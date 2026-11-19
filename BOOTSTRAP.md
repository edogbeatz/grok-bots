# BOOTSTRAP: instructions for a new Grok Bot

You are a Grok Bot on a new account owned by **Edgar Yan** (GitHub edogbeatz, Asia/Yerevan). This repo describes his bot system on his main account. Rebuild it here. Work in order and tell Edgar what you did at the end.

Load yourself first. Follow [MIGRATION.md](MIGRATION.md) before step 3. That file is the main coordinator. This file is the teammate bots.

## 0. Read first

1. [context/user.md](context/user.md), [context/standing-rules.md](context/standing-rules.md): follow these rules from now on.
1b. [context/core-agent-rules.md](context/core-agent-rules.md): how every bot works (own the lane, finish, prove, report format). [templates/](templates/): one role template per bot type.
2. `context/projects/*.md`: what each project is.
3. [context/bots-overview.md](context/bots-overview.md): the roster, the routines, and who hands off to whom.
4. [context/connectors.md](context/connectors.md): which connectors to reconnect.

Save the key facts from `context/user.md` and `standing-rules.md` to your own memory (UpdateMemory, profile type).

## 1. Check what already exists

List this account's bots first. If a bot with the same name exists, **update** it rather than creating a duplicate. Never delete a bot without asking Edgar.

## 2. Recreate the skills

For each folder in `skills/`, create a user skill with the same slug and the SKILL.md content verbatim (use the skill-authoring skill). Skills: explainer-video-render, legal-page-drafting, poster-typography, understand-outputs, warwin-brand-guide, warwin-character-bootstrap, warwin-character-generation, warwin-compliance-check, warwin-social-creative, zappi-pot, zappi-rail-review, zappi-send-fee-check. Three of those names are new in the 2026-11-19 main-bot skills export: `legal-page-drafting`, `understand-outputs`, and `zappi-send-fee-check`. `understand-outputs` is required by the main bot. `legal-page-drafting` has no owner bot in this repo yet (`zappi-legal` was named and not exported).

## 3. Recreate each bot

For each `bots/<slug>/` (skip `grok-bot`, which is you, the main assistant):

1. Read `bot.md`. Call **CreateAgent** with the bot's **name**. Build its instructions in this order: [context/standing-rules.md](context/standing-rules.md), then [context/core-agent-rules.md](context/core-agent-rules.md), then the template(s) the brief names on its first line (see the table below), then the text inside the "Instructions / persona" block **verbatim**. If the result is too long for CreateAgent, keep the standing rules and the brief whole, and send the core rules and template in the step 3 message with a request to save them to memory. Use the avatar shape/color listed if the tool supports it. Put it in the sidebar section listed (Caretrace, warwin, Zappi Product, Marketing).
2. If the instructions say "unknown, recover from the bot's settings" (warwin.casino, zappi-explainer-animation), still send the standing rules, the core rules and [templates/content-design-bot.md](templates/content-design-bot.md). Use the "What it does" summary as the brief only. Tell Edgar the real instructions are missing. Do not invent them. Zappi has a draft brief in [bots/zappi/bot.md](bots/zappi/bot.md). Use that draft, and tell Edgar he must confirm it. Open items are in [docs/defects.md](docs/defects.md).
3. Send the new bot one SendToAgent message containing: its `memory.md` facts (ask it to save them with UpdateMemory), its `skills.md` list, its `status.md`, and the routine block(s) below.
4. **Routines:** for each routine in `routines.md`, ask the bot to create it with UpdateRoutine `action: create`, using the exact name, schedule (cron, Asia/Yerevan) or trigger, timing, and the saved prompt verbatim. Routines marked **paused** must be created and then paused (or created with `enabled: false`). Skip the four Zappi "Watch PR #..." routines (their PRs merged long ago) unless Edgar wants them.
5. Ask the bot to confirm back in the core report format (Result, Changes, Proof, Risks). Do not let any bot run a first full job until Edgar asks or its schedule fires.

Templates per bot:

| Template | Bots |
|---|---|
| [templates/orchestrator.md](templates/orchestrator.md) | dr eggbot, Zappi (with coding-bot). Grok Bot (main) is you: use this template, do not create that bot. |
| [templates/coding-bot.md](templates/coding-bot.md) | caretrace-app, Zappi, zappi-test-swarm (with [templates/addon-money-tests.md](templates/addon-money-tests.md)) |
| [templates/research-bot.md](templates/research-bot.md) | Zappi rail review (with [templates/addon-money-tests.md](templates/addon-money-tests.md)), zappi-researcher, zappi-competitor-watch, zappi-site-audit, exhlab-m2-product, esp-toy-research, founder-move-scout |
| [templates/content-design-bot.md](templates/content-design-bot.md) | zappi-product-marketer, zappi-content, zappi-explainer-animation, caretrace-explainer, warwin-marketer, warwin.casino |

Recommended order: dr eggbot, Zappi, Zappi rail review, zappi-test-swarm, zappi-researcher, zappi-competitor-watch, zappi-product-marketer, zappi-content, zappi-site-audit, zappi-explainer-animation, caretrace-app, caretrace-explainer, warwin.casino, warwin-marketer, exhlab-m2-product, esp-toy-research, founder-move-scout.

## 4. Box folders

Create empty working folders some routines expect: `/workspace/founder-move/` (tracker.md, log.md), `/home/box/agent-data/rail-watch/`, `/workspace/warwin/routine_state/`, `/workspace/site-audit/`, `/workspace/arman-watch/`, `/workspace/bot-design-check/`, `/workspace/handoff/daily/`. The last three belong to the main bot. [MIGRATION.md](MIGRATION.md) says the box already has `/workspace/arman-watch/last_seen.json`. Read that file. Do not reset it.

## 5. Connectors

Give Edgar the list from [context/connectors.md](context/connectors.md) and ask him to connect each one (GitHub, Linear, Zappi MCP accounts, X, Context7, Google Drive/Docs/Sheets, Figma, Higgsfield, Trello, Telegram, Agent Vault). Never ask him to paste a token, seed, key, or recovery phrase into chat.

## 6. Report

Use the core report format. Tell Edgar: bots created/updated, routines created (and which are paused), skills created, connectors still to connect, and any bot whose instructions are unknown.

Ids in this repo are from the original account; new bots get new ids. Keep this repo as the source of truth and update it when bots change (see [SYNC.md](SYNC.md)). Open defects stay in [docs/defects.md](docs/defects.md) until Edgar answers them.
