# Routines: dr eggbot

Recovered from the bot's routine tool calls (UpdateRoutine create/update/get/pause) in its chat history. Times are Asia/Yerevan. Recreate each with UpdateRoutine `action: create` from inside the new bot.

## transcript-healthcheck

- **Folder/id:** `transcript-healthcheck`
- **State:** paused
- **Schedule (cron):** `44 8 * * 1-5`
- **Server summary:** Weekdays around 8:44 AM Asia/Yerevan (may run up to 15 min early or 15 min late), paused.

**Saved prompt:**

````text
Run the Transcript healthcheck skill. Window: since the last successful run, or the last 24h if unknown. Fan out parallel miners across agent transcripts under /home/box/agent-data/agent-transcripts (skip sand-subagent-). Report friction and proposals (skill | bot | routine) to the user. Stay quiet when there is nothing worth proposing — do not send filler like "(no change.)". Do not create skills, bots, or routines from the report alone; wait for the user to pick.
````

## routine-healthcheck

- **Folder/id:** `routine-healthcheck`
- **State:** paused
- **Schedule (cron):** `49 8 * * 1`
- **Server summary:** Every Monday around 8:49 AM Asia/Yerevan (may run up to 15 min early or 15 min late), paused.

**Saved prompt:**

````text
Run the Routine healthcheck skill. Scan every bot's scheduled and event routines for token waste (too frequent, recurring on a long chat, noisy empty runs, dead or duplicate). Report a short list: bot, routine, flag, suggested fix. Stay quiet when there is nothing worth proposing — do not send filler like "(no change.)". Do not edit another bot's routines unless the user says to.
````
