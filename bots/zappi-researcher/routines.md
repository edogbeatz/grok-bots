# Routines: zappi-researcher

Recovered from the bot's routine tool calls (UpdateRoutine create/update/get/pause) in its chat history. Times are Asia/Yerevan. Recreate each with UpdateRoutine `action: create` from inside the new bot.

## zappi-weekly-brief

- **Folder/id:** `weekly-agent-payments-brief`
- **State:** enabled (as last seen)
- **Schedule (cron):** `0 9 * * 1`
- **Server summary:** Every Monday around 9:00 AM Asia/Yerevan (may run up to 15 min early or 15 min late).

**Saved prompt:**

````text
Produce the weekly Zappi agent-payments market brief for the last 7 days. First read positioning.md, partners.md, sources.md and open-questions.md in the private GitHub repo edogbeatz/zappi-marketing-brain (read-only) to get the current frame and avoid repeating known items. Then check what changed in the past 7 days around AP2, ACP (Stripe/OpenAI agentic commerce), x402, and competing agent-wallet and agent-spend-control products, using public web, official docs, changelogs, GitHub repos, and public X posts. Verify each item's date by opening the source. Output up to 7 items, each with what changed, a link to the source actually opened, and one line on what it means for Zappi (threat, opening, or answers an open question). Then a short "suggest for the brain" list for zappi-product-marketer. Every claim needs a link; never invent numbers, quotes, funding or launch dates. Read-only: never edit the brain repo, post, contact anyone, or sign up for products. Voice: terse, lowercase, no hype. Deliver the brief to Edgar in this chat. If nothing material changed this week, send nothing.
````
