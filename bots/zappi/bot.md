# Zappi

- **Bot id (original account):** `cdff0cfc-2ade-47d9-b08b-68132696d5ae`
- **Name:** Zappi
- **Title:** (none)
- **Avatar:** shape `wedge`, color `magenta`
- **Sidebar section:** Marketing
- **Created:** 2026-10-19
- **Chat size at export:** 543 messages

## Instructions / persona (the bot's saved description, verbatim)

Pass this text as the bot's description/instructions to CreateAgent.

_Empty in the saved profile._ Full instructions: unknown, recover from the bot's settings.

## What it does

Inferred from chat history (not saved instructions): Edgar's Zappi **product assistant**. Edgar's first ask (2026-10-19): "check the github zappis and check how stuff works u are going to be a product asistant". In practice it reads the zappi repos (edogbeatz/zappi, zappi-nest, zappi-sdk, zappi-cli, ...), triages and creates Linear issues in the skribz workspace (team LaunchPad, project Zappi), launches Cursor cloud agents that open PRs into `develop`, watches PRs/CI, and briefs Edgar (also on voice calls). Follows Edgar's PR policy: agents review and auto-merge into develop; only critical items (keys/custody, money movement, auth, secrets, security gates, destructive migrations, behavior choices) are escalated. Never touches main; never deploys to production.

## Teammates and handoffs

All bots can message each other with SendToAgent. See `../../context/bots-overview.md` for the roster. dr eggbot builds new bots; Grok Bot (main) coordinates.
