---
name: zappi-rail-review
description: >-
  Use when running a Zappi rail and fee review: re-read live Spark and
  Flashnet/Orchestra docs and check the Zappi wiki and web code against them,
  for both the main wallet and pots.
---
# Zappi rail and fee review

Read-only pass. Findings only: never fix app code, never edit vendor docs, never sign, pay, or move funds, never touch mnemonics, keys, or seeds, never call keyed Orchestra endpoints or create deposit addresses. This is not a release sign-off. A local test is not a deploy.

Repo: `edogbeatz/zappi`. Read both `develop` and `main` and record each commit SHA. Read through the GitHub connector. Anything that writes goes through a cloud agent PR that Edgar merges. If the connector can't reach the repo, run the pass in a Cursor cloud agent. The Nest service (`zappi-nest`) isn't in this repo, so mark Nest behavior unknown.

## Steps
1. **Wiki:** `codebase/zappi-rail-review` (if present), `codebase/cashier`, `codebase/cashier-api` (fee charging model), `analyses/spark-orchestra-fee-charging`, `analyses/wallet-rail-consistency`, `codebase/rail-catalog`, `codebase/agent-pots`, and open money rows on `codebase/known-issues`. Note which pages exist on which branch.
2. **Vendor docs, fetched live** (start from the llms.txt indexes). Record each URL and the fetch date.
   - Spark (https://docs.spark.money/llms.txt): withdraw to L1, estimate fees, addressing, Lightning create/pay, tokens.
   - Flashnet (https://docs.flashnet.xyz/llms.txt): orchestra fees, pricing, quotes, deposit addresses / standing deposits, api errors. The old /products/orchestration/* URLs redirect.
3. **Code:** walk the scope and checks below. Re-open the cited files and cite path plus line numbers.
4. **Compare** vendor article vs wiki vs code and flag contradictions. Don't silently fix wiki history.
5. **Report**, then file durable findings in the wiki and `wiki/log.md` through a cloud agent PR.

## Scope
Spark native send/receive. Flashnet standing deposits (observation; `scanner_unavailable` shown as PanelError with a 60 s stale time). Orchestra on/off-ramp (estimate, quote, execute, refundAddress, ~2 min quote TTL). Fees on every live rail, main wallet and pots. Skip unilateral L1 exit (see the optional section) and the archived May Flashnet swap UI unless asked.

## Fee rule
One all-in quote and one confirm, showing gross, then network fee, then net received. No MetaMask gas popup. No native ETH/SOL balance in the cashier. Spark ExitSpeed stays server-side. USDB sent to a Zappi user, username, or wallet address is free. Catalog typicals are not live quotes. The client must not send `appFees` or `affiliateIds`.

## Traps
- The Orchestra QR is never `sparkAddress`.
- Dollar receive does not use `getStaticDepositAddress`.
- The Lightning Address is account-only; pot Lightning is invoice-only.
- For pot send to an external address, `refundAddress` is the pot's Spark address from the BFF.
- `scanner_unavailable` shows as PanelError with a 60 s stale time.
- Spark invoices fail closed on paste.
- The 501 paste fallback must not sign locally after `broadcastStarted`.
- Don't name Spark in UI copy.

## Report
Lead with a verdict: aligned, wiki stale, code stale, or vendor changed. State the refs and SHAs read, and say if this skill's repo copy is missing. Then a markdown table sorted by severity with columns Severity, Layer (article / wiki / web / nest), Location, Finding. Each finding gives the article URL and fetch date, wiki vs code vs article, wallet vs pot, and whether the fee is shown, quoted, deducted, or recorded. Keep implemented, tested, merged, and deployed distinct. Terse, tables over prose.

## Optional: unilateral exit (only when asked)
Source: https://docs.spark.money (Unilateral Exit page; index at https://docs.spark.money/llms.txt), pasted by Edgar 2026-10-20. Re-fetch before relying on it.
- A unilateral exit withdraws from Spark without anyone's permission, as a fallback if Spark is distrusted or shuts down.
- Only exit leaves over 16,348 sats; smaller ones cost more in fees than they're worth.
- The whole process must finish in a single session, and the wallet is unusable until it does.
- Transactions must be broadcast from root to leaves, in the exact order the CLI shows. Deeper leaves need more transactions.
- Bitcoin Core v29 is required (ephemeral anchors). The feature is in beta.
- Mainnet: bring your own L1 UTXOs for fees, handle timelocks manually (no `--testmode`), broadcast with `bitcoin-cli submitpackage '["node_tx","fee_bump_tx"]'`. A 131,072 sat deposit is recommended for better leaf sizes.
- Regtest only: `--testmode=true` auto-refreshes timelocks, and packages are pushed via the regtest mempool about 1 min apart.
- CLI: `sparkcli getleaves`, `sparkcli unilateralexit [--testmode=true]`, `sparkcli checktimelock <leaf-id>`, `sparkcli testonly_expiretimelock <leaf-id>`, `sparkcli signfeebump <psbt> <private_key>`.
- Review angle: check that the wiki (`codebase/l1-recovery`, known-issues SEC-L1-HONESTY-1) and any UI copy state these limits honestly: the minimum leaf size, single session, own UTXOs, beta. Never run the CLI or handle a key.
