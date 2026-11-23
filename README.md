# grok-bots

Portable export of Edgar Yan's (GitHub **edogbeatz**) whole Grok Bot setup: 23 bot folders, their instructions, routines, memory, skills, and shared context. Exported 2026-11-16 (Asia/Yerevan) from the original account. The main coordinator's second brain was refreshed from a snapshot on 2026-11-19, with a 17:10 addendum the same day, checked on 2026-11-21, and updated on 2026-11-23. The live main bot is Ari. Follow [MIGRATION.md](MIGRATION.md) first.

Use it when Edgar opens another Grok Bot account (or another system) and wants it to know what's going on and to have the same bots.

## Start here

1. [MIGRATION.md](MIGRATION.md): rebuild the main coordinator ("Grok Bot") and load its second brain.
2. [BOOTSTRAP.md](BOOTSTRAP.md): rebuild the other bots after that.

## Index

- [MIGRATION.md](MIGRATION.md): profile, memory, skills, routines, connectors, and a check list for the main bot.
- [BOOTSTRAP.md](BOOTSTRAP.md): step-by-step for the teammate bots.
- [context/user.md](context/user.md): who Edgar is.
- [context/standing-rules.md](context/standing-rules.md): gates for every bot. Rule 3 and rule 3b are split. The grok-bots daily sync may auto-merge to `main` (rule 3 exception). The zappi-nest auto-merge note is an open question, not a rule. A saved send rule covers Zappi `quote_send` to one dev test address. The address is not in this repo.
- [context/core-agent-rules.md](context/core-agent-rules.md): how every bot works.
- [context/connectors.md](context/connectors.md): what to reconnect. No credentials.
- [context/bots-overview.md](context/bots-overview.md): roster, routines, handoffs. As of 2026-11-23: 22 live bots (Ari plus 21 teammates). `zappi-test-swarm` is not live. Its folder stays.
- [context/projects/](context/projects/): one file per project.
- [bots/grok-bot/](bots/grok-bot/): the main coordinator, live name Ari (brief, memory, routines, skills, open items). Three routines, all enabled. Prompts and crons unchanged. `arman-slack-watch` resumed 2026-11-23. `/workspace/arman-watch/last_seen.json` exists. Do not copy it and do not reset it.
- [bots/](bots/): one folder per bot. Added 2026-11-23: `zappi-ux-judge-agent-side`, `zappi-ux-judge-ui-side`, `zappi-plugin-watch`, `zappi-daily-security`, and `fam` (empty brief; not invented). New-bot schedules are unconfirmed.
- [skills/](skills/): user skills. Three added on 2026-11-19: `understand-outputs`, `legal-page-drafting`, `zappi-send-fee-check`. `zappi-pot` replaced on 2026-11-21 and left as-is on 2026-11-23. Three added on 2026-11-23: `ux-writing-review`, `web-interface-guidelines`, `zappi`.
- [docs/defects.md](docs/defects.md): open items that need Edgar.
- [SYNC.md](SYNC.md): how to refresh this repo.
- [templates/](templates/): one role template per bot type.

Warwin bots share [context/projects/warwin-brain.md](context/projects/warwin-brain.md). That file is the Warwin knowledge base.

Each `bots/<slug>/` folder has:

- `bot.md`: name, original id, avatar, section, saved instructions, what it does.
- `routines.md`: each routine's name, schedule, timezone, state, and full saved prompt.
- `memory.md`: durable memory facts.
- `skills.md`: user skills it uses.
- `status.md`: short current state.

## What is NOT here

No logins, tokens, API keys, cookies, vault contents, pot seeds, spender keys, `~/.zappi/` files, or OAuth data. Connectors need reconnecting once (see [context/connectors.md](context/connectors.md)). Chat history is not copied, only summaries. Email addresses and phone numbers were removed.

The 2026-11-19 snapshot names a live bot `zappi-legal`. This repo has no folder for it. The 2026-11-23 roster still does not include it. `zappi-test-swarm` is not in the live agents folder. The folder stays. FAM has no brief.

## Fresh-account quick start

Tell the new Grok Bot: *"Read github.com/edogbeatz/grok-bots and follow MIGRATION.md, then BOOTSTRAP.md."*
