# grok-bots

Portable export of Edgar Yan's (GitHub **edogbeatz**) whole Grok Bot setup: 18 bots, their instructions, routines, memory, skills, and shared context. Exported 2026-11-16 (Asia/Yerevan) from the original account.

Use it when Edgar opens another Grok Bot account (or another system) and wants it to know what's going on and to have the same bots.

## Layout

- `BOOTSTRAP.md`: step-by-step instructions for a fresh Grok Bot. **Start here.**
- `context/`: who Edgar is (`user.md`), `standing-rules.md`, `connectors.md`, `bots-overview.md` (roster, routines, handoffs), and `projects/*.md`.
- Warwin bots share `context/projects/warwin-brain.md`. That file is the Warwin knowledge base.
- `bots/<slug>/`: one folder per bot:
  - `bot.md`: name, original id, avatar, section, full saved instructions (verbatim), what it does.
  - `routines.md`: each routine's name, schedule/trigger, timing, state, and full saved prompt.
  - `memory.md`: durable memory facts that could be recovered.
  - `skills.md`: user skills it uses.
  - `status.md`: short current state as of the export.
- `skills/<slug>/`: verbatim copies of the user skills (SKILL.md).
- [SYNC.md](SYNC.md): how to refresh this repo.

## What is NOT here

No logins, tokens, API keys, cookies, vault contents, pot seeds, spender keys, `~/.zappi/` files, or OAuth data. Connectors need reconnecting once (see [context/connectors.md](context/connectors.md)). Chat history is not copied, only summaries. Email addresses and phone numbers were removed.

## Fresh-account quick start

Tell the new Grok Bot: *"Read github.com/edogbeatz/grok-bots and follow BOOTSTRAP.md."*
