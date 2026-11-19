---
name: zappi-send-fee-check
description: >-
  Use when a user wants to send money out of a Zappi pot, asks what a send will
  cost, or asks which network is cheapest or fastest. Quotes rails one at a
  time, suggests the fastest and the cheapest rail, and never sends without the
  user's pick.
---
# Zappi send: check fees and suggest the best rails

## 1. Load the live rules first
1. Fetch `https://dev.zappi.money/pots/SKILL.md` (or the production `pots/SKILL.md`) fresh every session. If it changed since last time, read it again in full before going on. The live page wins over anything below.
2. Call `read_rule` `zappi-agent-rules` and `read_skill` `zappi-spend`. A send is refused until `zappi-spend` is read.
3. Call `get_pot_balance` for the paying pot. If the balance is null, stop and say it is unavailable. Do not guess.

## 2. Work out which rails can reach the destination
- Spark address, Zappi username, Zappi pot, or Zappi Lightning address: internal dollar send (USDB). It is free and instant, so it is both the fastest and the cheapest. Suggest it and stop there unless the user insists on a chain.
- `0x…` address: EVM chains (Ethereum, Base, Arbitrum, BNB, Polygon, Arc, Optimism, Robinhood…). Ask which chain the receiver supports if they did not say. A wrong chain can lose the money.
- Base58 Solana address: Solana. `T…` address: Tron. `bc1…`/`1…`/`3…`: Bitcoin mainnet. `lnbc…`: Lightning invoice.
- Call `list_send_assets`, then `list_send_networks` only for the asset the user wants (or the first likely one). Only use networks the tool returns. Never use deposit lists to choose a payout.

## 3. Pull quotes gradually, not all at once
A quote is a `send` call whose `allowance_pull` result you read but do not pull. It is free, but each one leaves a "pending" row and counts against rate limits. So quote in small steps:
1. **Step 1, shortlist (max 3 rails).** From the networks the tool returned, pick up to 3 rails using the starting order in section 5 (one likely cheapest, one likely fastest, and the user's named chain if any). Quote them one at a time. Wait for each result before the next call.
2. **Step 2, report early.** Show the user those quotes and your fastest and cheapest suggestion (section 6) right away. Do not wait for every rail.
3. **Step 3, widen only if needed.** Quote more rails, one at a time and at most 3 more, only when: the user asks, a shortlisted quote was refused, the fee is over 2% of the amount, or the user's receiver does not accept the shortlisted chains.
4. Never send parallel quotes. Never quote the same rail and amount twice. Do not retry a refused quote; report the reason word for word.
5. Bitcoin returns only an approve link (no fee before approval). Do not request it just to see the fee; say the fee is shown only after approval and is often much higher on mainnet.
6. Tell the user that leftover "pending" rows from quotes are not real sends.

## 4. How to read the fee fields
| Field | Where | Meaning |
|---|---|---|
| `grossCents` | send quote / confirm | What leaves the pot. |
| `networkFeeCents` | send quote / confirm | Zappi's payout fee for this send (includes chain gas). |
| `netCents` | send quote / confirm | What the payout sends to the address. `gross = fee + net`. |
| `feeCents` | catalog row, `wait_spend` | The fee when present. If missing, say "the fee is quoted before you confirm". |
| `minimumGrossCents` | catalog row | Smallest send on that rail. |
| `minWithdrawCents` / `maxWithdrawCents` | catalog row | Limits. Say the maximum when set. |
| `typicalFeeCopy` | catalog row | A hint only. Do not recite it as the fee. |
| `estimatedArrivalCopy` | catalog row | Arrival time hint. Use it to judge speed. |
| `minDepositCents`, `feeFloorCents`, `feeRatePct`, `receiveOnMinCents` | deposit address | Fees for receiving into a Zappi pot, not for sending. |

## 5. Starting order for the shortlist (staging, Nov 2026; recheck each run)
Use this only to choose what to quote first. The live quote always decides.
| Asset | Likely cheapest | Likely fastest / most reliable | Avoid for small amounts |
|---|---|---|---|
| Pot to pot | Internal USDB (free) | Internal USDB (instant) | Any chain |
| USDC | Solana (0.01), Arc (0.02) | Base (0.04, credited in about a minute) | Ethereum (0.09–0.13 plus receive cost) |
| USDT | Solana (0.01) for outside wallets; Arbitrum / BNB / Polygon (0.03) | Arbitrum or Base | Ethereum (0.12); Tron was refused |
| ETH | Any L2 (0.01 quoted) | Base or Arbitrum | Ethereum (real fee about 0.09); never into a Zappi deposit address |
| BTC | Spark | Lightning or Spark (seconds) | Mainnet (about 1,500 sats extra, slow) |

## 6. Suggest the fastest and the cheapest rail
1. Rank the quoted rails two ways:
   - **Cheapest:** lowest total cost to the receiver = `networkFeeCents` plus the known receive-side cost when the destination is a Zappi deposit address (section 7).
   - **Fastest (best performance):** shortest `estimatedArrivalCopy`, then the most reliable rail (no known held or lost deposits in section 7). Ties go to the cheaper one.
2. Show a short table, cheapest first: rail, fee, the receiver gets, arrival time.
3. Give two suggestions in plain sentences, for example: "Cheapest: Solana, 0.01 fee, the receiver gets 2.29. Fastest: Base, about 1 minute, 0.04 fee." If one rail wins both, say so in one sentence.
4. Warn when a fee is over 2% of the amount, and strongly warn over 5%. Suggest a cheaper rail or a larger single send.
5. Ask the user to pick. Use the host's choice UI with labels copied exactly from the tool.
6. Never send, pull, or approve until the user picks a rail and says yes to the exact gross / fee / net.

## 7. Known gaps between quote and real cost (staging, Nov 2026; recheck each run)
- Ethereum stablecoins: the payout quote is close (about 0.11–0.13 USD), but a Zappi Ethereum deposit address loses about another 0.35 USD on receipt.
- ETH payouts: quoted 0.01, real about 0.09 on Ethereum. ETH into a Zappi ETH deposit address is not credited ("could not verify the sender").
- Solana USDT into a Zappi deposit address was never credited, and Solana USDC was held. Fine for outside wallets.
- BTC mainnet: no fee before approval; about 1,500 sats extra seen on a 6,500-sat send.
- The catalog may return no `feeCents`. Then rely on the live `send` quote only.
- Check the amount against minimums and maximums before quoting. Never learn a limit by sending.

## 8. After the user picks
- Run the send with the allowance pull only when `spenderPublicKey` matches. Confirm with `idempotencyKey` = requestId and `sparkTxId`. Never print a recovery phrase.
- Repeat gross, fee, net and the txid from the result. On `pending_recovery`, say it is in flight and do not send again.
- For approve links: give the link and how long it lasts (`expiresAt`). Keep calling `wait_spend` until sent, denied or expired, and tell the user the result straight away.
- Afterwards, compare the real result with the quote. If the receiver got less than `netCents`, tell the user the difference.
