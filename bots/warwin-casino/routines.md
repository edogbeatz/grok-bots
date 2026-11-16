# Routines: warwin.casino

Recovered from the bot's routine tool calls (UpdateRoutine create/update/get/pause) in its chat history. Times are Asia/Yerevan. Recreate each with UpdateRoutine `action: create` from inside the new bot.

## Warwin Trello: things for Edgar

- **Folder/id:** `warwin-trello-things-for-edgar`
- **State:** enabled (as last seen)
- **Schedule (cron):** `0 10,13,16,19 * * 1-5`
- **Timing:** flexible
- **Server summary:** Every 3 hours on weekdays, 10:00 AM – 7:00 PM (may run up to 15 min early or 15 min late), next run 11/6/2026, 3:59:00 PM GMT+4.

**Saved prompt:**

````text
Check the "WarWin — Marketing" Trello board (Trello connector) for anything new that concerns Edgar (his Trello username is edogbeatz) since the last check. Keep the time of the last check in /workspace/warwin/routine_state/trello_last_check.txt; if that file is missing, look back 24 hours. Write the current time to it at the end of each run.

Count it as concerning Edgar when any of these is true:
- a comment mentions @edogbeatz or Edgar, or replies to or asks about his work (for example Babken asking for new designs, files or changes)
- a new comment or activity appears on a card where edogbeatz is a member or where he commented before
- a card is assigned to him or he's added to it, or a due date on one of his cards is today, tomorrow or already overdue
- a new card lands in the Design list, or a design or creative request lands anywhere on the board

Skip Edgar's own comments and actions, and skip routine moves that need nothing from him. Never post, comment on or change anything in Trello; this routine only reads.

Deliver the result to Edgar in this Grok Bot chat: one short message listing each item in plain words, saying who asked for what, on which card (linked with its Trello URL), and what's due. If nothing new concerns him, send nothing.
````
