# Routines: Zappi daily security

Checked 2026-11-23, Asia/Yerevan. Live routine objects were not confirmed on disk.

## daily security review

- **State:** specified in the profile. Not confirmed live.
- **Schedule:** unconfirmed
- **Intended cron:** `0 21 * * *` (21:00 Asia/Yerevan). If a scheduler has no timezone, 17:00 UTC.
- **Timezone:** Asia/Yerevan
- **Not:** 03:00 Asia/Yerevan. That hour is the frontend pull-request review.
- **Delivers to:** the channel Edgar picks. Default is this chat.

The intended prompt is the system prompt in [bot.md](bot.md). This file does not add a second prompt.
