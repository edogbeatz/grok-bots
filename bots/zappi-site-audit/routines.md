# Routines: zappi-site-audit

Recovered from the bot's routine tool calls (UpdateRoutine create/update/get/pause) in its chat history. Times are Asia/Yerevan. Recreate each with UpdateRoutine `action: create` from inside the new bot.

## Monthly site re-audit

- **Folder/id:** `monthly-site-re-audit`
- **State:** paused
- **Schedule (cron):** `0 10 1 * *`
- **Server summary:** On the 1st of every month around 10:00 AM Asia/Yerevan (may run up to 15 min early or 15 min late), paused.

**Saved prompt:**

````text
Monthly re-audit of the one primary site. User local time is already on this schedule (10:00 on the 1st).

Setup gate first: read /workspace/site-audit/SETUP.md (also accept /workspace/full-site-audit/SETUP.md). If setup_complete is not true or site_url is empty, do not invent a site and do not fake Lighthouse/PSI/lab numbers. Stay quiet if still waiting on a URL.

If site_url is set: re-run the same crawl_scope (homepage, nav-linked top pages, one example of each public template; cap about 30 pages unless SETUP says otherwise). Gentle crawl. Public pages only. Cover all six dimensions: SEO technical, content, speed, accessibility, CRO, schema/structured data. If you cannot measure something, mark it unmeasured and say why.

Compare to baseline/ and the last reports/. Write reports/YYYY-MM-DD.md, reports/YYYY-MM-DD-diff.md, and copy the full report to reports/latest.md. Diff sections: fixed / still open / new / regressions. Do not claim a fix without evidence. Update baseline/ snapshots (titles, small HTML hashes or saved copies of critical pages — keep them small). Put screenshots and tool links under evidence/YYYY-MM-DD/.

Chat the diff even if there is no material change (monthly always reports). Attach the report if you can. Never invent metrics, traffic, rankings, or conversion rates. Do not change the live site. Do not expand into other bots' jobs.
````

## Weekly audit self-improve

- **Folder/id:** `weekly-audit-self-improve`
- **State:** paused
- **Schedule (cron):** `0 9 * * 1`
- **Server summary:** Every Monday around 9:00 AM Asia/Yerevan (may run up to 15 min early or 15 min late), paused.

**Saved prompt:**

````text
Weekly quiet self-improvement for Site Audit only. Stay inside this bot's job (one-site SEO, content, speed, a11y, CRO, schema audits and how they are reported). Never expand into other bots' jobs (growth posting, inboxes, prices, invoices, VM admin).

Read /workspace/site-audit/SETUP.md, /workspace/site-audit/IMPROVEMENTS.md, and any recent files under reports/ if they exist.

Do ONE concrete improvement to how you audit or report (a checklist note, evidence convention, scoring rubric line, crawl-scope reminder, or a gap you hit on a real audit). Append a short dated entry to /workspace/site-audit/IMPROVEMENTS.md. Do not invent a site or lab metrics. Do not run a full audit on this wake unless SETUP already has a site_url and you are only tightening process docs.

Stay silent after logging the improvement unless a human decision is required (for example still no site_url after setup, or a broken monthly routine). No filler "all good" ping.
````
