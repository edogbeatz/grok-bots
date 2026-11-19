# Move the main Grok Bot

## Handover (2026-11-19)

Edgar is starting a new main bot on 2026-11-19.
You are that bot. Read this file first.

Recreate these three routines. Prompts, crons, and timezone are in [bots/grok-bot/routines.md](bots/grok-bot/routines.md). Timezone for all three is Asia/Yerevan.

1. `arman-slack-watch` — cron `0,30 9-21 * * *` — flexible, about 15 minutes.
2. `weekly-bot-design-check` — cron `0 10 * * 1` — flexible, about 15 minutes.
3. `grok-bots-daily-sync` — cron `0 22 * * *` — flexible, 15 minutes early or 30 minutes late.

The old box already has this file. Read it. Do not reset it. Do not invent a new cursor.

- `/workspace/arman-watch/last_seen.json`
  - Arman DM: `D0CFX3D2TEZ`
  - #bots: `C0CKZUSP03S`

The other bots come after this, in [BOOTSTRAP.md](BOOTSTRAP.md).

Write in short sentences. Edgar is not a native English speaker.
Do not paste a token, a key, a seed, a session, or a recovery phrase into chat.
Do not copy anything from `~/.zappi/`.

## 1. You are this bot

You are the new main bot.
Do not create a second bot named Grok Bot.

Read these files before you change anything:

1. [context/user.md](context/user.md)
2. [context/standing-rules.md](context/standing-rules.md)
3. [context/core-agent-rules.md](context/core-agent-rules.md)
4. [templates/orchestrator.md](templates/orchestrator.md)
5. [bots/grok-bot/bot.md](bots/grok-bot/bot.md)

## 2. Set the profile

1. Set the short description to the stock line in [bots/grok-bot/bot.md](bots/grok-bot/bot.md): "A teammate with its own computer that takes real work off your plate."
2. Set the full instructions to this stack, in this order:
   - [context/standing-rules.md](context/standing-rules.md)
   - [context/core-agent-rules.md](context/core-agent-rules.md)
   - [templates/orchestrator.md](templates/orchestrator.md)
   - the brief inside [bots/grok-bot/bot.md](bots/grok-bot/bot.md)
3. Use avatar shape `blob` and color `black` if the tool allows it.
4. Sidebar section: Unassigned.

The old account id was `9bce498a-82dd-46ba-a2a8-4c9e2248c738`. The new bot gets a new id. Leave the old id in the repo.

## 3. Load the memory

Open [bots/grok-bot/memory.md](bots/grok-bot/memory.md).
Save each bullet with UpdateMemory.
Use the heading as the type when the tool has that type:

- Profile
- Behavior rules
- People and orgs
- Workstreams

If the tool has fewer types, save the bullet and keep the heading words in the text.
Do not save the open questions as rules. They stay in [bots/grok-bot/status.md](bots/grok-bot/status.md).

## 4. Install the skills

For each folder in [skills/](skills/), create a user skill with the same name.
Copy `SKILL.md` word for word.

This bot must have `understand-outputs`. The brief uses it.

The 2026-11-19 export added three skills:

- `understand-outputs`
- `legal-page-drafting`
- `zappi-send-fee-check`

Install the older skills too, so the account matches the export:

- `explainer-video-render`
- `poster-typography`
- `warwin-brand-guide`
- `warwin-character-bootstrap`
- `warwin-character-generation`
- `warwin-compliance-check`
- `warwin-social-creative`
- `zappi-pot`
- `zappi-rail-review`

`legal-page-drafting` has no owner bot in this repo. The snapshot names `zappi-legal`. That bot was not exported. Install the skill. Do not invent the bot.

## 5. Create the routines

Open [bots/grok-bot/routines.md](bots/grok-bot/routines.md).
Create each routine with UpdateRoutine, action `create`.
Use the same name, the same cron, timezone Asia/Yerevan, flexible timing, and the saved prompt word for word.

| Routine | Cron | Timezone | When it sends |
|---|---|---|---|
| `arman-slack-watch` | `0,30 9-21 * * *` | Asia/Yerevan | Only when Arman has a new message. Flexible, about 15 minutes. |
| `weekly-bot-design-check` | `0 10 * * 1` | Asia/Yerevan | Monday about 10:00. First run named in the snapshot: 2026-11-23. Sends on a breach, a move of more than 10 points, or the first run. |
| `grok-bots-daily-sync` | `0 22 * * *` | Asia/Yerevan | About 22:00. Flexible, 15 minutes early or 30 minutes late. Sends only when the second brain changed. May auto-merge to `main` on edogbeatz/grok-bots only, under the rule 3 exception. |

Create these folders if they are missing:

- `/workspace/arman-watch/`
- `/workspace/bot-design-check/`
- `/workspace/handoff/daily/`

`/workspace/arman-watch/last_seen.json` should already be on the box. Read it. Do not reset it.

Do not run a full check now. Let the schedule fire.
Do not reply on Slack from the Arman watch. The prompt forbids that.

The Arman schedule may change. Edgar has not chosen hourly or weekdays-only. Keep the cron above until he does.

## 6. Connect the tools

Ask Edgar to connect each one. He signs in himself.
Do not ask him to paste a token.

From the 2026-11-19 snapshot, this bot uses:

1. Gmail
2. Linear
3. Zappi (account name `edog`)
4. Trello
5. Google Drive
6. Figma
7. Higgsfield
8. Firecrawl
9. Vercel
10. Slack
11. cursor-github
12. cursor-origin
13. X

Details and older names are in [context/connectors.md](context/connectors.md).
The 2026-11-16 export also named Agent Vault, Composio, and Railway for this bot. The morning snapshot does not list them. The 17:10 addendum says this bot has no Railway access. Ask Edgar before you connect Agent Vault or Composio. Do not connect Railway unless he asks.

Slack ids to expect after connect:

- Edgar: U0CG0CXMUR4
- Arman Mosikyan: U0CFM0XN9C7
- #all-zappi: C0CFM0VGF2B
- #bots: C0CKZUSP03S

## 7. Check this list

Tell Edgar the result in the core report format: Result, Changes, Proof, Risks.

- [ ] The short description is the stock line.
- [ ] The instructions include standing rules, core rules, the orchestrator template, and the brief.
- [ ] Rule 3 and rule 3b are both present, and they stay split.
- [ ] The rule 3 exception quotes Edgar: "Auto-merge the daily grok-bots update to main. Add this as a rule 3 exception for grok-bots only." It covers edogbeatz/grok-bots only.
- [ ] The zappi-nest auto-merge note is still an open question. It is not a rule. You did not auto-merge that repo.
- [ ] Each memory bullet in [bots/grok-bot/memory.md](bots/grok-bot/memory.md) is saved.
- [ ] `understand-outputs` is installed.
- [ ] The other skill folders in [skills/](skills/) are installed, with the same text.
- [ ] `arman-slack-watch` exists, cron `0,30 9-21 * * *`, Asia/Yerevan, prompt matches [routines.md](bots/grok-bot/routines.md).
- [ ] `weekly-bot-design-check` exists, cron `0 10 * * 1`, Asia/Yerevan, prompt matches [routines.md](bots/grok-bot/routines.md).
- [ ] `grok-bots-daily-sync` exists, cron `0 22 * * *`, Asia/Yerevan, prompt matches [routines.md](bots/grok-bot/routines.md).
- [ ] `/workspace/arman-watch/last_seen.json` was read and left as it was.
- [ ] `/workspace/bot-design-check/` and `/workspace/handoff/daily/` exist.
- [ ] The connector list in section 6 was shown to Edgar. Nothing was connected with a pasted token.
- [ ] No secret, token, key, seed, session, or `~/.zappi/` file was written into this repo.
- [ ] Open items in [bots/grok-bot/status.md](bots/grok-bot/status.md) were shown to Edgar and left open.

Then follow [BOOTSTRAP.md](BOOTSTRAP.md) for the teammate bots.

## What this file does not rebuild

- `zappi-legal`. The snapshot names it. There is no folder.
- "Zappi Rail Test" as its own bot. The repo folder for rail tests is [bots/zappi-test-swarm/](bots/zappi-test-swarm/). Edgar must say if that is the same bot.
- Edgar's email. The snapshot had one. This repo does not store email addresses.
- Chat history. Only the facts in [bots/grok-bot/memory.md](bots/grok-bot/memory.md).
- The old Monday 12:00 export idea in [SYNC.md](SYNC.md). Edgar replaced it with `grok-bots-daily-sync` at 22:00 Asia/Yerevan. `weekly-bot-design-check` is a different job. It does not export the repo.
