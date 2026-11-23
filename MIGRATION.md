# Move the main bot (Ari)

## Handover (as of 2026-11-23)

The live main coordinator is Ari.
Live id: `46fc624e-4e27-4e05-a280-f79c6e0b71fa`.
The original-account id `9bce498a-82dd-46ba-a2a8-4c9e2248c738` stays as history.
You are that bot when you rebuild it. Read this file first. Do not create a second coordinator.

Recreate these three routines. Prompts, crons, and timezone are in [bots/grok-bot/routines.md](bots/grok-bot/routines.md). Timezone for all three is Asia/Yerevan. All three are enabled. Prompts and crons are unchanged.

1. `arman-slack-watch` — cron `0,30 9-21 * * *` — flexible, about 15 minutes. Enabled. Resumed 2026-11-23 after Slack was reconnected. Prompt and schedule unchanged.
2. `weekly-bot-design-check` — cron `0 10 * * 1` — flexible, about 15 minutes. Enabled. First run about 09:53 Asia/Yerevan on 2026-11-23. No gate breaches. Prompt and schedule unchanged.
3. `grok-bots-daily-sync` — cron `0 22 * * *` — flexible, 15 minutes early or 30 minutes late. Enabled. Ran 2026-11-20 22:36 and 2026-11-21. On 2026-11-22 nothing meaningful had changed. Prompt and schedule unchanged.

`/workspace/arman-watch/last_seen.json` exists as of 2026-11-23. Read it. Do not copy it into this repo. Do not reset it. Do not invent a new cursor.

- `/workspace/arman-watch/last_seen.json` (exists on 2026-11-23)
  - Arman DM: `D0CFX3D2TEZ`
  - #bots: `C0CKZUSP03S`

The other bots come after this, in [BOOTSTRAP.md](BOOTSTRAP.md).

Write in short sentences. Edgar is not a native English speaker.
Do not paste a token, a key, a seed, a session, or a recovery phrase into chat.
Do not copy anything from `~/.zappi/`.

## 1. You are this bot

You are the main bot. The live name is Ari.
Do not create a second coordinator.

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

The original-account id was `9bce498a-82dd-46ba-a2a8-4c9e2248c738`. The live id as of 2026-11-23 is `46fc624e-4e27-4e05-a280-f79c6e0b71fa`. A later new account gets its own id. Leave both ids in the repo. The live name is Ari. The folder stays `bots/grok-bot/`.

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
- `zappi-pot` (replaced 2026-11-21)
- `zappi-rail-review`

`legal-page-drafting` has no owner bot in this repo. The snapshot names `zappi-legal`. That bot was not exported. Install the skill. Do not invent the bot.

The 2026-11-23 export added three skills. Install them word for word. Do not edit `zappi-pot`. It already matches the 2026-11-21 text.

- `ux-writing-review`
- `web-interface-guidelines`
- `zappi`

## 5. Create the routines

Open [bots/grok-bot/routines.md](bots/grok-bot/routines.md).
Create each routine with UpdateRoutine, action `create`.
Use the same name, the same cron, timezone Asia/Yerevan, flexible timing, and the saved prompt word for word.
Create all three enabled. Prompts and crons match [routines.md](bots/grok-bot/routines.md). Do not change them.

| Routine | Cron | Timezone | When it sends |
|---|---|---|---|
| `arman-slack-watch` | `0,30 9-21 * * *` | Asia/Yerevan | Enabled. Resumed 2026-11-23. Only when Arman has a new message. Flexible, about 15 minutes. Prompt and schedule unchanged. `last_seen.json` exists. Do not reset it. |
| `weekly-bot-design-check` | `0 10 * * 1` | Asia/Yerevan | Enabled. Monday about 10:00. First run about 09:53 Asia/Yerevan on 2026-11-23. No gate breaches. Sends on a breach, a move of more than 10 points, or the first run. Prompt and schedule unchanged. |
| `grok-bots-daily-sync` | `0 22 * * *` | Asia/Yerevan | Enabled. About 22:00. Flexible, 15 minutes early or 30 minutes late. Sends only when the second brain changed. Ran 2026-11-20 22:36 and 2026-11-21. Nothing sent on 2026-11-22. May auto-merge to `main` on edogbeatz/grok-bots only, under the rule 3 exception. Prompt and schedule unchanged. |

Create these folders if they are missing:

- `/workspace/arman-watch/`
- `/workspace/bot-design-check/`
- `/workspace/handoff/daily/`

`/workspace/arman-watch/last_seen.json` exists as of 2026-11-23. Read it. Do not reset it. Do not invent a cursor. Do not copy it into this repo.

Do not run a full check now. Let the schedule fire.
Do not reply on Slack from the Arman watch. The prompt forbids that.

The Arman schedule may change. Edgar has not chosen hourly or weekdays-only. Keep the cron above until he does.

## 6. Connect the tools

Ask Edgar to connect each one. He signs in himself.
Do not ask him to paste a token.

On the live Ari bot as of 2026-11-23, these are connected:

1. Slack
2. Linear
3. Zappi MCP
4. cursor-github
5. cursor-origin
6. X

Not in the live catalog. Still to connect, one card at a time:

1. Gmail
2. Trello
3. Google Drive
4. Figma
5. Higgsfield
6. Firecrawl
7. Vercel

On a new account, ask Edgar to connect each one again. He signs in himself.

Details and older names are in [context/connectors.md](context/connectors.md).
The 2026-11-16 export also named Agent Vault, Composio, and Railway for this bot. Ask Edgar before you connect Agent Vault or Composio. Do not connect Railway unless he asks.

A saved send rule allows Zappi `quote_send` to one dev test address. Do not write the address into this repo. Standing rule 14 (merge one zappi-nest pull request only when Edgar asks) is unchanged.

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
- [ ] The live name is Ari. Live id `46fc624e-4e27-4e05-a280-f79c6e0b71fa` is recorded. The original id is still in the repo.
- [ ] `arman-slack-watch` exists, enabled, cron `0,30 9-21 * * *`, Asia/Yerevan, prompt matches [routines.md](bots/grok-bot/routines.md). It resumed 2026-11-23. Prompt and schedule were not changed.
- [ ] `weekly-bot-design-check` exists, enabled, cron `0 10 * * 1`, Asia/Yerevan, prompt matches [routines.md](bots/grok-bot/routines.md). First run about 09:53 Asia/Yerevan on 2026-11-23. No gate breaches.
- [ ] `grok-bots-daily-sync` exists, enabled, cron `0 22 * * *`, Asia/Yerevan, prompt matches [routines.md](bots/grok-bot/routines.md). It ran 2026-11-20 22:36 and 2026-11-21. Nothing was sent on 2026-11-22.
- [ ] `/workspace/arman-watch/last_seen.json` exists. It was read and left as it was. It was not invented and not copied into the repo.
- [ ] `ux-writing-review`, `web-interface-guidelines`, and `zappi` are installed. `zappi-pot` was not edited.
- [ ] The Zappi `quote_send` saved send rule is loaded. The address is not in the repo.
- [ ] `/workspace/bot-design-check/` and `/workspace/handoff/daily/` exist.
- [ ] The connector list in section 6 was shown to Edgar. Nothing was connected with a pasted token.
- [ ] No secret, token, key, seed, session, or `~/.zappi/` file was written into this repo.
- [ ] Open items in [bots/grok-bot/status.md](bots/grok-bot/status.md) were shown to Edgar and left open.

Then follow [BOOTSTRAP.md](BOOTSTRAP.md) for the teammate bots.

## What this file does not rebuild

- `zappi-legal`. The snapshot names it. There is no folder.
- "Zappi Rail Test" as its own bot. The repo folder for rail tests is [bots/zappi-test-swarm/](bots/zappi-test-swarm/). As of 2026-11-23 the live bot is missing. Bootstrap id `3e67ebda-9451-464b-b703-d7134c12c3d1` is in deleted-agents. No replacement id. Keep the folder. Do not recreate it unless Edgar asks.
- FAM. The profile description is empty. Do not invent a brief. See [bots/fam/](bots/fam/).
- The five folders added 2026-11-23 (`fam`, `zappi-daily-security`, `zappi-plugin-watch`, `zappi-ux-judge-agent-side`, `zappi-ux-judge-ui-side`). Their schedules are unconfirmed. Rebuild them from [BOOTSTRAP.md](BOOTSTRAP.md) after this file. Do not create the judge routines until Edgar's skill and one on-demand run are done.
- Edgar's email. The snapshot had one. This repo does not store email addresses.
- Chat history. Only the facts in [bots/grok-bot/memory.md](bots/grok-bot/memory.md).
- The old Monday 12:00 export idea in [SYNC.md](SYNC.md). Edgar replaced it with `grok-bots-daily-sync` at 22:00 Asia/Yerevan. `weekly-bot-design-check` is a different job. It does not export the repo.
