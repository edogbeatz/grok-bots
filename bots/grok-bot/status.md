# Status: Ari (Grok Bot) (as of 2026-11-23, Asia/Yerevan)

- Checked 2026-11-23. No secrets. No email addresses. No phone numbers.
- Live name: Ari. Live id: `46fc624e-4e27-4e05-a280-f79c6e0b71fa`. Original-account id `9bce498a-82dd-46ba-a2a8-4c9e2248c738` stays as history. This folder stays `bots/grok-bot/`.
- The main-bot move is done. Rebuild steps remain in [MIGRATION.md](../../MIGRATION.md).
- Routines: 3 exist, 3 enabled, 0 paused. Prompts and crons are unchanged. See [routines.md](routines.md).
- `arman-slack-watch` is enabled. It resumed on 2026-11-23 after Slack was reconnected. `/workspace/arman-watch/last_seen.json` exists. Do not paste its contents. Do not reset it. DM `D0CFX3D2TEZ` and #bots `C0CKZUSP03S` may stay in this repo. Cron stays `0,30 9-21 * * *`, Asia/Yerevan.
- `weekly-bot-design-check` is enabled. First run completed about 09:53 Asia/Yerevan on 2026-11-23. Baseline: `/workspace/bot-design-check/2026-11-23.json`. No gate breaches. The first run sent a report, as required.
- `grok-bots-daily-sync` is enabled. It ran 2026-11-20 22:36 and 2026-11-21. On 2026-11-22 nothing meaningful had changed, so it sent nothing. The 2026-11-23 pass is a manual mid-day snapshot.
- Skills: the twelve skills already on main stay, including `zappi-pot` (not edited; 24666 bytes, sha256 `1726bc747b274998320351187ca9659fc647c891245a9f64cbe321a84050cc73`). Added 2026-11-23: `ux-writing-review`, `web-interface-guidelines`, `zappi`.
- Registered computers at about 17:57 Asia/Yerevan: Dogs MacBook Pro 25088 online; iPhone 17 Pro offline; Alisas iMac registered and offline. No command was run on the iMac.

## Arman watch log (2026-11-19, Asia/Yerevan)

On 2026-11-21, `/workspace/arman-watch/last_seen.json` was missing. On 2026-11-23 the file exists again. The notes below are from 2026-11-19. They are not a paste of the cursor file.

- 13:13 Arman DM: send error "Flashnet quote missing a bitcoin amount out." Cause: zappi-nest `quoteSparkUsdbToBtc` read `amountOut`. Vendor docs name it `estimatedOut`. Fixed on zappi-nest `develop` by PR 317 (merged 14:45), which uses `readQuoteDestinationAmount`. The Slack reply draft to Arman is out of date. Discard it.
- 15:42 and 16:34 Arman DM: "Bitcoin deposits could not be read" (`CHAIN_UNAVAILABLE`). zappi-nest `static-btc-utxos` returns 502. Public blockstream.info returns 429 (700 requests an hour per IP). Web PR 652 merged 16:24. Likely fix: Edgar or Arman sets `BITCOIN_ESPLORA_URL` on dev Railway. The value is a secret. This repo does not store it. Not verified live.

## Infra

- dev.zappi.money runs on Railway, server `railway-hikari`. It does not run on Vercel. This bot has no Railway access.
- Vercel team `edogbeatzs-projects` hosts the Zappi web previews only. Morning snapshot team id: `team_SUGmwVcJBDW6NVQyyACxbJl1`.
- Merges on 2026-11-19: zappi-nest `develop` PRs 315 and 317-325. Zappi web `develop` PRs 642-653 and 655.

## Open items for Edgar

These are questions. They are not rules. Do not start the unapproved work.

1. Arman watch: switch to hourly, or run on weekdays only? This is a cost question. It stays open. Until Edgar chooses, keep `0,30 9-21 * * *`. The routine is enabled again as of 2026-11-23.
2. zappi-nest auto-merge exception to standing rule 3b: still unconfirmed. See the open question in [context/standing-rules.md](../../context/standing-rules.md). Until Edgar confirms it, rule 3b stands: auto-merge only into `develop` on edogbeatz/zappi.
3. Zappi Rail Test name versus the repo folder [bots/zappi-test-swarm/](../zappi-test-swarm/). The live bot is missing. See that folder's status.
4. Not started. Needs Edgar's OK: a cloud agent for Linear 1-1102, 1-1103, and 1-1104. A relaunch for 1-1038 and 1-1030.
5. The main-bot move is done. The live main bot is Ari (`46fc624e-4e27-4e05-a280-f79c6e0b71fa`).
6. Morning brief routine: offered at 09:00 Asia/Yerevan (`0 9 * * *`). Still waiting for Edgar's topics. Do not create it yet.
7. Connect the remaining tools one card at a time: Gmail, Trello, Google Drive, Figma, Higgsfield, Firecrawl, and Vercel. Ask before Agent Vault or Composio. Do not connect Railway unless Edgar asks.
8. Waiting on Edgar for: the Warwin brain location, briefs for warwin.casino and zappi-explainer-animation, confirmation of the Zappi brief, and moving the bots into sidebar sections himself. Sidebar section lists were not in live settings on 2026-11-23.
9. zappi-ux-judge-agent-side and zappi-ux-judge-ui-side: wait for a skill from Edgar, then one on-demand run, then create the weekly routines (Tuesday 11:00 and Wednesday 11:00 Asia/Yerevan). `ux-writing-review` and `web-interface-guidelines` were added to the skills folder on 2026-11-23. This check does not confirm that Edgar handed those skills to the judge bots, or that the routines exist. Both schedules are unconfirmed.
10. FAM (`99372476-f9b5-489b-93f8-9022d5b23587`) has an empty profile description. It needs a brief. Do not invent one.
11. zappi-test-swarm is not in the live agents folder. The bootstrap id `3e67ebda-9451-464b-b703-d7134c12c3d1` is the only id in deleted-agents. No replacement id was found. Confirm with Edgar whether to recreate it. The repo folder stays until he says.
12. `legal-page-drafting` still has no bot. Do not invent zappi-legal.
13. Alisas iMac is registered and was offline at this check.

The grok-bots daily sync to `main` is approved. It is the rule 3 exception. It is not an open item.

## Could not place from the snapshot

- Live bot name `zappi-legal`: still no folder, no brief, no routines.
- Slack email for Edgar: not stored. The Slack user id is in [memory.md](memory.md).
- `.library-fingerprint`: hashes only. Not a skill. Not committed.
- `last_seen.json`: exists on the box. Contents not copied.
