# Status: Grok Bot (as of 2026-11-19)

- Snapshot date: 2026-11-19. No secrets in the snapshot.
- Role: main coordinator. Second brain is this folder plus [context/](../../context/).
- Routines: 2 enabled (`arman-slack-watch`, `weekly-bot-design-check`). Prompts are in [routines.md](routines.md).
- Skills added from the snapshot export: `understand-outputs`, `legal-page-drafting`, `zappi-send-fee-check`.
- Earlier export status (2026-11-16): the chat was setting up this repo. That note is superseded by this file.

## Open items for Edgar

These are questions. They are not rules. Do not start the unapproved work.

1. Arman watch: keep the current schedule (`0,30 9-21 * * *`, every day), switch to hourly, or run on weekdays only?
2. Add a zappi-nest auto-merge exception to standing rule 3b? The Zappi bot says Edgar chose this on 2026-11-18. It is not confirmed. See the open question in [context/standing-rules.md](../../context/standing-rules.md). Until Edgar confirms it, rule 3b stands: auto-merge only into `develop` on edogbeatz/zappi.
3. Send the core rules and templates to "Zappi Rail Test", or skip that bot? The repo has no bot with that exact name. The rail-test folder is [bots/zappi-test-swarm/](../zappi-test-swarm/).
4. Unapproved. Do not start: a cloud agent for Linear 1-1102, 1-1103, and 1-1104. Do not relaunch agents for 1-1038 and 1-1030.

## Could not place from the snapshot

- Live bot name `zappi-legal`: no folder, no brief, no routines.
- Slack email for Edgar: the snapshot included one. This repo does not store email addresses. The Slack user id is in [memory.md](memory.md).
- `.library-fingerprint` from the skills archive: hashes only. Not a skill. Not committed.
