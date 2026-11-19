# Sync

Planned: a weekly routine on the main Grok Bot (e.g. Mondays 12:00 Asia/Yerevan) that re-exports the bots into this repo and commits. Not created yet; ask Edgar first.

A different Monday routine already exists: `weekly-bot-design-check` in [bots/grok-bot/routines.md](bots/grok-bot/routines.md) (10:00 Asia/Yerevan). It checks whether bots follow the design. It does not export this repo.

Each sync:
1. Read `/home/box/agent-data/agents/*/profile.json` (name, description, avatar) and `/home/box/agent-data/settings.json` `sidebarSections` (read-only).
2. For routines, read each bot's transcript (ReadTranscript `in=<bot id>`) for UpdateRoutine create/update/get/pause calls, or ask each bot to list its routines with full prompts.
3. Copy `/home/box/agent-data/workflows/*` into `skills/`.
4. Regenerate `bots/<slug>/*.md`, keep `status.md` short.
5. Run the secret scan below, then commit and push through a PR or direct push as Edgar prefers.

Never export: store.db `blobEncryptionKey`, box-secrets.json, host-secrets.json, chrome-cookie-seed.json, vault data, `~/.zappi/`, OAuth data, email addresses, phone numbers.

Secret scan:

```bash
grep -rniE 'sk-[a-z0-9]{10,}|ghp_[a-z0-9]{10,}|zpc_[a-z0-9]{6,}|BEGIN [A-Z ]*PRIVATE KEY|xox[bp]-|AKIA[0-9A-Z]{16}|[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}' .
```
