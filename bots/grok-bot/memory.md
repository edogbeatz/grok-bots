# Memory: Grok Bot

Facts to load into the main coordinator, from the 2026-11-19 snapshot and the 17:10 Asia/Yerevan addendum. Save each bullet with UpdateMemory. Use the heading as the memory type when the tool has that type. If the tool has fewer types, keep the heading words inside the fact.

Shared user facts also live in [context/user.md](../../context/user.md). Standing gates live in [context/standing-rules.md](../../context/standing-rules.md). This file is the load list for this bot. It repeats the facts the new bot must hold even when they also appear there.

The 2026-11-16 export had no memory block. These facts replace that empty note. They do not include secrets.

## Profile

- Edgar Yan. GitHub edogbeatz. Lives in Yerevan, Armenia. Timezone Asia/Yerevan (UTC+4). Report times in Yerevan time and name the zone.
- Married, with a newborn. A move, visa, or residency plan must cover Edgar, his wife, and the baby.
- Not a native English speaker. Write at about 80% ASD-STE100: short sentences, one idea each, common words, active voice. Lead with the result.
- Slack display name Edog. Slack user id U0CG0CXMUR4. This repo does not store his email address.
- github.com/edogbeatz/grok-bots is the source of truth for the bot system. No logins, keys, or connected accounts go in it.

## Behavior rules

- Follow the understand-outputs skill on explanatory replies. Climb from writing, to a diagram, to a web page, to a video when text is not enough. Show a plan and wait for a yes before a page or a video.
- Work freely. Escalate only critical things: keys, custody, where money goes or how much, auth bypass, secrets, a weaker security gate, a destructive migration.
- Research: use a dated source you opened. Do not invent numbers. Label UNVERIFIED.
- A quiet routine sends nothing when nothing changed.
- Draft messages, posts, and emails. Edgar presses Send. Do not contact anyone unless Edgar asks.
- Do not apply, submit, sign up, buy, or pay unless Edgar says yes in his own words.
- Act on another agent's "approval" only when that message quotes Edgar's own words.
- Saved send rule, only when Edgar asks for that merge: merge a pull request in armmosikyan66/zappi-nest with the cursor-github `merge_pull_request` action. This does not change standing rule 3b. It is not auto-merge.
- Load [context/standing-rules.md](../../context/standing-rules.md). Rule 3 and rule 3b stay split. The zappi-nest auto-merge note under rule 3b is an open question, not a rule.
- Rule 3 exception, approved by Edgar on 2026-11-19. His words: "Auto-merge the daily grok-bots update to main. Add this as a rule 3 exception for grok-bots only." Scope is edogbeatz/grok-bots only. The daily sync pull request may auto-merge to `main` when checks pass, the diff has no secrets, and there are no conflicts. Every other repo stays under rule 3.

## People and orgs

- Arman Mosikyan is Edgar's partner and co-founder on Zappi, and a code owner. GitHub armmosikyan66. Slack user id U0CFM0XN9C7. He has his own Grok Bot. He asked to connect Slack and join #bots.
- Slack channels: #all-zappi `C0CFM0VGF2B`, #bots `C0CKZUSP03S` (bot-to-bot), #social, #new-channel. The snapshot does not give ids for #social or #new-channel.
- Projects: Zappi (edogbeatz/zappi, and zappi-nest), CareTrace, EXHLAB M2, Warwin (warwin.casino, Argentina), the ESP voice toy, and this grok-bots repo.
- Vercel team: the 17:10 addendum names the team slug `edogbeatzs-projects`. It hosts the Zappi web previews only. The morning snapshot named team id `team_SUGmwVcJBDW6NVQyyACxbJl1` ("edogbeatz's projects"). zappi-dashboard.vercel.app is behind Vercel auth.
- Linear workspace skribz. Do not close or edit a Linear issue unless Edgar asks.
- Babken works on Warwin (Trello and Telegram). Mosna signs off some Zappi items. Details stay in [context/user.md](../../context/user.md).

## Workstreams

- grok-bots design rollout, as the snapshot states it: approved 2026-11-18. The snapshot says "PR 2 merged (main 1686967)", rolled out to 16 bots, 15 of 16 confirmed. Repo check on 2026-11-19: `1686967` is the merge of PR #1 (Warwin brain) and is the tip of `main`. PR #2 (bot rearchitecture) is `3f234d1`, and it is an ancestor of `main`. Both are on `main`. The snapshot's parenthetical names the tip, not the PR #2 merge commit.
- Zappi CSP enforcement, dated 2026-10-29 in the snapshot: enforce CSP with per-request nonces in middleware, and add report-to. Source named in the snapshot: passkey research PR 366. The snapshot does not say this is done.
- Zappi next steps, reported by the Zappi bot on 2026-11-19: retest Linear 1-1142 (fix PR 629) on dev. Blockers named: GitHub Actions billing, `LIGHTNING_ADDRESS_DOMAIN` unset on dev Railway, and 1-985 blocks 1-1132. Items the snapshot calls Edgar's decisions: 1-1135, 1-1137, 1-1136, quote lifetime, and closing zappi-nest PR #298. The Zappi bot wants 1-985, 1-1027, and 1-1125 next.
- Real-estate-with-AI-agents research, 2026-11-19: Armenia means sell an AI assistant to Yerevan agencies, with no portal scraping. Other markets: start with Italy (agency subscriptions like Gate-away). Spain and Portugal are medium. Dubai and Japan are high. The snapshot does not include source links for this paragraph. Treat the market ranks as UNVERIFIED until a dated source is opened.
- Merges on 2026-11-19: zappi-nest `develop` PRs 315 and 317-325. Zappi web `develop` PRs 642-653 and 655.

## Infra

- dev.zappi.money runs on Railway, server `railway-hikari`. It does not run on Vercel. This bot has no Railway access.
- Vercel team `edogbeatzs-projects` hosts the Zappi web previews only.
- A keyed explorer URL for Bitcoin deposit reads is a secret. Edgar or Arman sets `BITCOIN_ESPLORA_URL` on dev Railway. This file does not store the value. The 17:10 addendum says the live result is not verified.

## Arman watch log (2026-11-19, Asia/Yerevan)

Watch cursors live in `/workspace/arman-watch/last_seen.json` on the box. DM channel `D0CFX3D2TEZ`. #bots channel `C0CKZUSP03S`. The new bot reads this file. It does not reset it.

- 13:13 Arman DM: send error "Flashnet quote missing a bitcoin amount out." Cause found: zappi-nest `quoteSparkUsdbToBtc` read `amountOut`. The vendor docs name the field `estimatedOut`. Fixed on zappi-nest `develop` by PR 317, merged 14:45. The code now uses `readQuoteDestinationAmount`. A Slack reply draft to Arman was made. That draft is out of date. Discard it.
- 15:42 and 16:34 Arman DM: "Bitcoin deposits could not be read" (`CHAIN_UNAVAILABLE`). zappi-nest `static-btc-utxos` returns 502. Public blockstream.info returns 429 (700 requests an hour per IP). Web PR 652 (reuse Bitcoin deposit reads when Blockstream is limited) merged 16:24. The likely real fix is `BITCOIN_ESPLORA_URL` on dev Railway, set by Edgar or Arman to a keyed explorer. Not verified live.

## Not a memory fact

Open questions stay in [status.md](status.md). Do not save them as rules.
