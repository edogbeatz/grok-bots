# Status: Grok Bot (as of 2026-11-21, Asia/Yerevan)

- Checked 2026-11-21. No secrets. No email addresses.
- Role: main coordinator. Edgar is starting a new main bot on 2026-11-19. That bot reads [MIGRATION.md](../../MIGRATION.md) first.
- Routines: 3 exist, 2 enabled (`weekly-bot-design-check`, `grok-bots-daily-sync`), 1 paused (`arman-slack-watch`). Prompts are in [routines.md](routines.md).
- `arman-slack-watch` is paused after two Slack auth failures (`needsAuth`). It paused itself at 2026-11-20 09:37 Asia/Yerevan. `/workspace/arman-watch/last_seen.json` is missing. DM `D0CFX3D2TEZ` and #bots `C0CKZUSP03S` were not read. To resume: reconnect Slack, then UpdateRoutine resume. Prompt and schedule unchanged. Cron stays `0,30 9-21 * * *`, Asia/Yerevan.
- `grok-bots-daily-sync` ran 2026-11-20 22:36 and 2026-11-21. It stays enabled.
- Skills: `skills/zappi-pot/SKILL.md` was replaced on 2026-11-21. It adds an opt-in allowance offer after pairing and after a send `approveUrl`. Other skill files are unchanged from the 17:10 archive.
- Earlier export status (2026-11-16): the chat was setting up this repo. That note is superseded by this file.

## Arman watch log (2026-11-19, Asia/Yerevan)

On the 2026-11-21 check, `/workspace/arman-watch/last_seen.json` is missing. DM `D0CFX3D2TEZ` and #bots `C0CKZUSP03S` were not read. The notes below are from 2026-11-19.

- 13:13 Arman DM: send error "Flashnet quote missing a bitcoin amount out." Cause: zappi-nest `quoteSparkUsdbToBtc` read `amountOut`. Vendor docs name it `estimatedOut`. Fixed on zappi-nest `develop` by PR 317 (merged 14:45), which uses `readQuoteDestinationAmount`. The Slack reply draft to Arman is out of date. Discard it.
- 15:42 and 16:34 Arman DM: "Bitcoin deposits could not be read" (`CHAIN_UNAVAILABLE`). zappi-nest `static-btc-utxos` returns 502. Public blockstream.info returns 429 (700 requests an hour per IP). Web PR 652 merged 16:24. Likely fix: Edgar or Arman sets `BITCOIN_ESPLORA_URL` on dev Railway. The value is a secret. This repo does not store it. Not verified live.

## Infra

- dev.zappi.money runs on Railway, server `railway-hikari`. It does not run on Vercel. This bot has no Railway access.
- Vercel team `edogbeatzs-projects` hosts the Zappi web previews only. Morning snapshot team id: `team_SUGmwVcJBDW6NVQyyACxbJl1`.
- Merges on 2026-11-19: zappi-nest `develop` PRs 315 and 317-325. Zappi web `develop` PRs 642-653 and 655.

## Open items for Edgar

These are questions. They are not rules. Do not start the unapproved work.

1. Arman watch: switch to hourly, or run on weekdays only? This is a cost question. It stays open. Until Edgar chooses, keep `0,30 9-21 * * *`. The routine stays paused. To resume: reconnect Slack, then UpdateRoutine resume.
2. zappi-nest auto-merge exception to standing rule 3b: still unconfirmed. See the open question in [context/standing-rules.md](../../context/standing-rules.md). Until Edgar confirms it, rule 3b stands: auto-merge only into `develop` on edogbeatz/zappi.
3. Zappi Rail Test: send the core rules, or skip that bot? The repo has no bot with that exact name. The rail-test folder is [bots/zappi-test-swarm/](../zappi-test-swarm/).
4. Not started. Needs Edgar's OK: a cloud agent for Linear 1-1102, 1-1103, and 1-1104. A relaunch for 1-1038 and 1-1030.
5. Edgar is moving to a new main bot on 2026-11-19. The new bot reads [MIGRATION.md](../../MIGRATION.md) first.

The grok-bots daily sync to `main` is approved. It is the rule 3 exception. It is not an open item.

## Could not place from the snapshot

- Live bot name `zappi-legal`: no folder, no brief, no routines.
- Slack email for Edgar: the morning snapshot included one. This repo does not store email addresses. The Slack user id is in [memory.md](memory.md).
- `.library-fingerprint` from both skills archives: hashes only. Not a skill. Not committed.
