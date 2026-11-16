# Connectors and plugins (names only, no credentials)

Reconnect each once on the new account (OAuth / sign-in done by Edgar). Nothing here contains tokens.

| Connector | Used by | Purpose |
|---|---|---|
| GitHub (Cursor built-in source control) | Zappi, rail review, caretrace-app, caretrace-explainer, test-swarm, product-marketer | repos edogbeatz/zappi, armmosikyan66/zappi-nest, zappi-sdk, zappi-cli, CareTraceApp, CareTraceVideo, edogbeatz/zappi-marketing-brain (legacy pointer) |
| Cursor cloud agents / Cursor Origin | Zappi, caretrace-app, rail review | PRs into develop |
| Linear (workspace skribz) | Zappi, rail review, test-swarm, main | issues, epics |
| Zappi MCP (accounts: chocho, calocho, fourth) | test-swarm, rail review, main, Zappi | pots, deposits, sends on staging. Log in via Zappi MCP login link that Edgar approves. Auto-review allow rule: "Use the user-zappi send tool to make payments to Spark addresses" |
| X (built-in public reads + X plugin) | competitor-watch, researcher, main | public post search |
| Context7 | rail review | vendor docs |
| Google Drive / Docs / Sheets | warwin.casino, warwin-marketer | Warwin brief and exports |
| Figma (two connections: free and paid) | warwin.casino | designs |
| Higgsfield | warwin.casino, warwin-marketer | brand-girl images (Soul ID) |
| Trello | warwin.casino | "WarWin — Marketing" board |
| Telegram (designer bot account) | warwin.casino | posts to the Warwin team thread only when Edgar says so |
| Agent Vault | main | password vault (never export) |
| Composio | main | misc |
| Railway (skill) | main, Zappi | staging infra |

Box state worth recreating (empty): `/workspace/founder-move/` (tracker.md, log.md), `/home/box/agent-data/rail-watch/` (rail snapshot), `/workspace/warwin/` (exports, routine_state), `/workspace/site-audit/SETUP.md`.
