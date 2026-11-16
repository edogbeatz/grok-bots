# Routines: zappi-competitor-watch

Recovered from the bot's routine tool calls (UpdateRoutine create/update/get/pause) in its chat history. Times are Asia/Yerevan. Recreate each with UpdateRoutine `action: create` from inside the new bot.

## competitor-weekly-digest

- **Folder/id:** `competitor-weekly-digest`
- **State:** enabled (as last seen)
- **Schedule (cron):** `0 10 * * 1`
- **Server summary:** Every Monday around 10:00 AM Asia/Yerevan (may run up to 15 min early or 15 min late), next run 10/26/2026, 10:07:00 AM GMT+4.

**Saved prompt:**

````text
Write this week's Zappi competitor digest, following my agent profile (watch list, relevance ranking, rules, anti-jobs). Cover only the last 7 days; older items are context and must show their date. Check X public reads, the web and news, product changelogs and docs, and GitHub (releases, new repos, feature commits) for every company on the watch list, including Flashnet's partners and integrations. Also search for new agent-payment, agent-wallet, MCP-payments, 402 (x402, L402) and Bitcoin-stablecoin projects and propose additions with a reason.

Format: start with the current watch list so Edgar can trim it. Then the 3 moves that matter most to Zappi, one sentence each on why. Then a table per competitor with what changed, the date, a source link, and relevance (high/med/low). Then new entrants. Every finding needs a dated source link; no link, no finding. Never invent numbers or quotes; label rumors UNVERIFIED; keep facts separate from my read, and label the read as opinion. Don't repeat items from earlier digests or alerts in this chat unless something new happened. Never post, reply, or message anyone, and never use the Zappi connector or any wallet or payment tool.

Deliver the digest to Edgar in this chat only. If a competitor had nothing new, say so briefly in its table row rather than dropping it.
````

## competitor-alert-scan

- **Folder/id:** `competitor-alert-scan`
- **State:** enabled (as last seen)
- **Schedule (cron):** `0 9,18 * * *`
- **Server summary:** Every day around 9:00 AM and 6:00 PM Asia/Yerevan (may run up to 15 min early or 15 min late), next run 10/21/2026, 9:09:00 AM GMT+4.

**Saved prompt:**

````text
Scan Zappi's competitor watch list (from my agent profile, plus Flashnet partners and any additions Edgar approved) for big news since the last scan: a competitor launch, a funding round, a new partnership, an acquisition, or a protocol change in x402, L402, AP2 or ACP. Use X public reads, the web and news, changelogs, and GitHub releases. Skip anything already reported in this chat.

For each big item, send one short message: what happened, when (Asia/Yerevan time or date), the source link, and why it matters to Zappi, labeled as opinion. Never invent numbers; label unconfirmed posts UNVERIFIED. Never post, reply, or message anyone, and never use the Zappi connector or any wallet or payment tool.

Results go to Edgar in this chat only. If nothing big happened, send nothing at all: no "all quiet" message.
````
