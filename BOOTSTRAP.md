# BOOTSTRAP: instructions for a new Grok Bot

You are a Grok Bot on a new account owned by **Edgar Yan** (GitHub edogbeatz, Asia/Yerevan). This repo describes his bot system on his main account. Rebuild it here. Work in order and tell Edgar what you did at the end.

## 0. Read first

1. `context/user.md`, `context/standing-rules.md`: follow these rules from now on.
2. `context/projects/*.md`: what each project is.
3. `context/bots-overview.md`: the roster, the routines, and who hands off to whom.
4. `context/connectors.md`: which connectors to reconnect.

Save the key facts from `context/user.md` and `standing-rules.md` to your own memory (UpdateMemory, profile type).

## 1. Check what already exists

List this account's bots first. If a bot with the same name exists, **update** it rather than creating a duplicate. Never delete a bot without asking Edgar.

## 2. Recreate the skills

For each folder in `skills/`, create a user skill with the same slug and the SKILL.md content verbatim (use the skill-authoring skill). Skills: explainer-video-render, poster-typography, warwin-brand-guide, warwin-character-bootstrap, warwin-character-generation, warwin-compliance-check, warwin-social-creative, zappi-pot, zappi-rail-review.

## 3. Recreate each bot

For each `bots/<slug>/` (skip `grok-bot`, which is you, the main assistant):

1. Read `bot.md`. Call **CreateAgent** with the bot's **name** and, as its description/instructions, the text inside the "Instructions / persona" block **verbatim**. Use the avatar shape/color listed if the tool supports it. Put it in the sidebar section listed (Caretrace, warwin, Zappi Product, Marketing).
2. If the instructions say "unknown, recover from the bot's settings" (Zappi, warwin.casino, zappi-explainer-animation), create the bot with the "What it does" summary as its description and tell Edgar it needs his real instructions.
3. Send the new bot one SendToAgent message containing: its `memory.md` facts (ask it to save them with UpdateMemory), its `skills.md` list, its `status.md`, and the routine block(s) below.
4. **Routines:** for each routine in `routines.md`, ask the bot to create it with UpdateRoutine `action: create`, using the exact name, schedule (cron, Asia/Yerevan) or trigger, timing, and the saved prompt verbatim. Routines marked **paused** must be created and then paused (or created with `enabled: false`). Skip the four Zappi "Watch PR #..." routines (their PRs merged long ago) unless Edgar wants them.
5. Ask the bot to confirm back. Do not let any bot run a first full job until Edgar asks or its schedule fires.

Recommended order: dr eggbot, Zappi, Zappi rail review, zappi-test-swarm, zappi-researcher, zappi-competitor-watch, zappi-product-marketer, zappi-content, zappi-site-audit, zappi-explainer-animation, caretrace-app, caretrace-explainer, warwin.casino, warwin-marketer, exhlab-m2-product, esp-toy-research, founder-move-scout.

## 4. Box folders

Create empty working folders some routines expect: `/workspace/founder-move/` (tracker.md, log.md), `/home/box/agent-data/rail-watch/`, `/workspace/warwin/routine_state/`, `/workspace/site-audit/`.

## 5. Connectors

Give Edgar the list from `context/connectors.md` and ask him to connect each one (GitHub, Linear, Zappi MCP accounts, X, Context7, Google Drive/Docs/Sheets, Figma, Higgsfield, Trello, Telegram, Agent Vault). Never ask him to paste a token, seed, key, or recovery phrase into chat.

## 6. Report

Tell Edgar: bots created/updated, routines created (and which are paused), skills created, connectors still to connect, and any bot whose instructions are unknown.

Ids in this repo are from the original account; new bots get new ids. Keep this repo as the source of truth and update it when bots change (see `SYNC.md`).
