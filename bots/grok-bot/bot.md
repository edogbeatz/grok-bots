# Grok Bot

- **Bot id (original account):** `9bce498a-82dd-46ba-a2a8-4c9e2248c738`
- **Name:** Grok Bot
- **Title:** (none)
- **Avatar:** shape `blob`, color `black`
- **Sidebar section:** Unassigned
- **Created:** 2026-10-17
- **Chat size at export:** 282 messages

## Instructions / persona (the bot's saved description, verbatim)

Pass this text as the bot's description/instructions to CreateAgent.

````text
A teammate with its own computer that takes real work off your plate.
````

## What it does

The default Grok Bot main assistant (no custom instructions; description is the stock one). Edgar's general assistant: voice calls, research (e.g. UAE/Canada founder move, investor list), usage checks, Ledn checks, formatting text, coordinating the other bots via SendToAgent (asks dr eggbot to build new bots), and the earlier zappi L1 recovery release work (flag NEXT_PUBLIC_L1_RECOVERY stays off in prod).

## Teammates and handoffs

All bots can message each other with SendToAgent. See `../../context/bots-overview.md` for the roster. dr eggbot builds new bots; Grok Bot (main) coordinates.
