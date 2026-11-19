# Connectors and plugins (names only, no credentials)

Reconnect each once on the new account (OAuth / sign-in done by Edgar). Nothing here contains tokens.

| Connector | Used by | Purpose |
|---|---|---|
| GitHub (Cursor built-in source control) | Zappi, rail review, caretrace-app, caretrace-explainer, test-swarm, product-marketer, main | repos edogbeatz/zappi, armmosikyan66/zappi-nest, zappi-sdk, zappi-cli, CareTraceApp, CareTraceVideo, edogbeatz/zappi-marketing-brain (legacy pointer) |
| cursor-github | main, coding bots | GitHub reads and pull-request actions. The saved send rule uses `merge_pull_request` on armmosikyan66/zappi-nest only when Edgar asks. |
| cursor-origin | main | Origin reads |
| Cursor cloud agents / Cursor Origin | Zappi, caretrace-app, rail review | PRs into develop |
| Linear (workspace skribz) | Zappi, rail review, test-swarm, main | issues, epics |
| Zappi MCP (accounts: chocho, calocho, fourth; main bot snapshot also names `edog`) | test-swarm, rail review, main, Zappi | pots, deposits, sends on staging. Log in via Zappi MCP login link that Edgar approves. Auto-review allow rule: "Use the user-zappi send tool to make payments to Spark addresses" |
| X (built-in public reads + X plugin) | competitor-watch, researcher, main | public post search |
| Context7 | rail review | vendor docs |
| Gmail | main | Edgar's mail. Draft only unless Edgar asks to send. |
| Google Drive / Docs / Sheets | warwin.casino, warwin-marketer, main | Warwin brief and exports |
| Figma (two connections: free and paid) | warwin.casino, main | designs |
| Higgsfield | warwin.casino, warwin-marketer, main | brand-girl images (Soul ID) |
| Firecrawl | main | web research |
| Vercel | main | team "edogbeatz's projects" (`team_SUGmwVcJBDW6NVQyyACxbJl1`). zappi-dashboard.vercel.app is behind Vercel auth. |
| Slack | main | Edgar U0CG0CXMUR4. Arman U0CFM0XN9C7. #all-zappi `C0CFM0VGF2B`, #bots `C0CKZUSP03S`, #social, #new-channel. |
| Trello | warwin.casino, main | "WarWin — Marketing" board |
| Telegram (designer bot account) | warwin.casino | posts to the Warwin team thread only when Edgar says so |
| Agent Vault | main | password vault (never export). Named in the 2026-11-16 export. The 2026-11-19 main-bot snapshot does not list it. Ask Edgar. |
| Composio | main | misc. Same note as Agent Vault. |
| Railway (skill) | main, Zappi | staging infra. Same note as Agent Vault. |

Box state worth recreating (empty): `/workspace/founder-move/` (tracker.md, log.md), `/home/box/agent-data/rail-watch/` (rail snapshot), `/workspace/warwin/` (exports, routine_state), `/workspace/site-audit/SETUP.md`, `/workspace/arman-watch/` (last_seen.json, written by the main bot), `/workspace/bot-design-check/` (weekly JSON, written by the main bot).
