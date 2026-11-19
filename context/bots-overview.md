# Bots overview

| Bot | Folder | Original id | Section | Job (short) |
|---|---|---|---|---|
| caretrace-app | `bots/caretrace-app/` | `7123b01e-2489-47c8-8934-6cd7ce8ac874` | Caretrace | My only job: turn CareTraceApp issues and Edgar's asks into small, verified pull requests, shipped through Cursor cloud agents. Casual, shor… |
| caretrace-explainer | `bots/caretrace-explainer/` | `e3ce860d-498a-473a-bce2-3da276673781` | Caretrace | My only job: make short CareTrace explainer videos from code. Each video is an HTML/GSAP scene that I render frame by frame to an MP4 with m… |
| dr eggbot | `bots/dr-eggbot/` | `2fb508be-a443-4f91-887c-1df047f8ac24` | Unassigned | Designs high-quality Grok Bots. Asks a few preference questions, then creates them with CreateAgent. Coding bots get the poteto-mode bar (on… |
| esp-toy-research | `bots/esp-toy-research/` | `fd1b4b42-7333-43e2-93ce-37eb34574c44` | Unassigned | My only job: research for Edgar's ESP-based personal-assistant toy (kids and adults). I report findings with dated source links. I never wri… |
| exhlab-m2-product | `bots/exhlab-m2-product/` | `72de6273-d4bb-40e3-b867-7b992bb7064f` | Unassigned | My only job: help Edgar develop an app based on EXHLAB's M2 equation by researching competition, understanding the target user, and clarifyi… |
| founder-move-scout | `bots/founder-move-scout/` | `e89eb0e7-fe7c-48e6-b6af-d1088662ee50` | Unassigned | My only job: research investors and visa or residency routes in the UAE and Canada for Edgar's two startups, CareTrace (care and health-trac… |
| Grok Bot | `bots/grok-bot/` | `9bce498a-82dd-46ba-a2a8-4c9e2248c738` | Unassigned | Main coordinator. Stock description is one line. Brief, memory, routines, and open items are in the folder. Rebuild with [MIGRATION.md](../MIGRATION.md). |
| warwin-marketer | `bots/warwin-marketer/` | `10be853a-4007-4be2-9380-40743fc00d48` | warwin | My only job: Warwin's marketing for Argentina. I turn the designer brief into a go-to-market plan, a posting calendar and per-piece campaign… |
| warwin.casino | `bots/warwin-casino/` | `67c31a6f-99a8-4403-8776-6115dd27aa35` | warwin | Inferred from chat history (not saved instructions): Warwin's **designer bot** (warwin.casino). Started 2026-11-02 from the Google Doc `Warw… |
| Zappi | `bots/zappi/` | `cdff0cfc-2ade-47d9-b08b-68132696d5ae` | Marketing | Inferred from chat history (not saved instructions): Edgar's Zappi **product assistant**. Edgar's first ask (2026-10-19): "check the github … |
| Zappi rail review | `bots/zappi-rail-review/` | `0d6c7816-e8c6-44c8-a5bc-55cf47b5f764` | Zappi Product | My only job: keep Zappi's rails honest against the live Spark, Flashnet and Orchestra docs. I have two on-demand modes. "review" (or "run it… |
| zappi-competitor-watch | `bots/zappi-competitor-watch/` | `9f21027b-840f-49e2-9f8e-2e84444b3ca3` | Unassigned | My only job: watch Zappi's competitors and report who is building what in agentic and crypto-first payments. I report in my own chat and now… |
| zappi-content | `bots/zappi-content/` | `ba54d60d-ebf7-4316-98a3-75ddd87244d4` | Marketing | My only job: draft Zappi's owned content for the agent-payments path, meaning docs intros and demo walkthrough scripts, partner explainers, … |
| zappi-explainer-animation | `bots/zappi-explainer-animation/` | `919c79bc-2513-42c5-88af-69ff3f364771` | Marketing | Inferred from its only message (2026-10-21): helps make Zappi's explainer animation, from script and storyboard through to finished video. N… |
| zappi-product-marketer | `bots/zappi-product-marketer/` | `805dc36a-1e88-4a40-bc8c-e91bb413a849` | Marketing | My only job: own Zappi's positioning and turn it into copy drafts. I keep the Zappi Marketing Brain true and current, and I draft landing, d… |
| zappi-researcher | `bots/zappi-researcher/` | `760e4db4-5614-4b56-84b7-371820abd898` | Marketing | My only job: a weekly market brief for Zappi's agent-payments story. Each Monday I check what changed in the last 7 days around AP2, ACP (St… |
| zappi-site-audit | `bots/zappi-site-audit/` | `545078a1-ad51-4882-a31b-51fdb5661dd4` | Marketing | SEO + content + speed + a11y + CRO + schema audit. Scored, P0/P1/P2, evidence URLs. Monthly diff. No invented metrics.… |
| zappi-test-swarm | `bots/zappi-test-swarm/` | `fe1ea36f-e6d6-4ca9-9010-cbaf12930b50` | Unassigned | My only job: orchestrate Zappi pot and account tests across internal and external rails, then turn every real failure into a Linear Todo in … |

## Routines

| Bot | Routine | State |
|---|---|---|
| dr eggbot | transcript-healthcheck | paused |
| dr eggbot | routine-healthcheck | paused |
| esp-toy-research | esp-toy-weekly | enabled (as last seen) |
| exhlab-m2-product | exhlab-m2-weekly | enabled (as last seen) |
| founder-move-scout | weekly-founder-move-digest | enabled (as last seen) |
| Grok Bot | arman-slack-watch | enabled (snapshot 2026-11-19) |
| Grok Bot | weekly-bot-design-check | enabled (snapshot 2026-11-19; first run named 2026-11-23) |
| warwin.casino | Warwin Trello: things for Edgar | enabled (as last seen) |
| Zappi | Watch PR #464 (develop test fix) | paused |
| Zappi | Watch PR #447 auto-merge | paused |
| Zappi | Zappi develop PR auto-fixer | paused |
| Zappi | Watch PR #467 overlap allowlist | paused |
| Zappi | Watch PR #468 overlap warning gate | paused |
| Zappi rail review | Daily Flashnet, Orchestra, Spark and Grid change watch | enabled (as last seen) |
| Zappi rail review | Rail incident check (Flashnet, Spark, Lightspark) | enabled (as last seen) |
| zappi-competitor-watch | competitor-weekly-digest | enabled (as last seen) |
| zappi-competitor-watch | competitor-alert-scan | enabled (as last seen) |
| zappi-researcher | zappi-weekly-brief | enabled (as last seen) |
| zappi-site-audit | Monthly site re-audit | paused |
| zappi-site-audit | Weekly audit self-improve | paused |

## Handoffs

- **dr eggbot** designs and creates new bots (CreateAgent), then messages each new bot its setup task (usually a routine to create). Bot-creation requests go through it.
- **Grok Bot (main)** is Edgar's general assistant and coordinator. It relays asks to other bots with SendToAgent. Its second brain (2026-11-19) is in [bots/grok-bot/](../bots/grok-bot/). Rebuild it with [MIGRATION.md](../MIGRATION.md). It runs `arman-slack-watch` and `weekly-bot-design-check`.
- The 2026-11-19 snapshot names a live bot `zappi-legal` and a live bot "Zappi Rail Test". This repo has no `zappi-legal` folder. "Zappi Rail Test" is not a folder name. The rail-test bot in this repo is `zappi-test-swarm`. The snapshot header says 16 live teammates and then lists 18 names.
- **Zappi** (product assistant) owns Linear triage and cloud-agent PRs for zappi web/Nest; asked dr eggbot for zappi-competitor-watch.
- **Zappi marketing team:** zappi-researcher (weekly market brief) feeds "suggest for the brain" items to zappi-product-marketer (positioning, wiki/marketing/ in the zappi repo), which feeds zappi-content (docs intros, demo scripts). zappi-competitor-watch is competitors only. zappi-site-audit audits the site. zappi-explainer-animation is unused so far.
- **Zappi engineering checks:** Zappi rail review (vendor docs vs wiki vs code, daily rail watch, files LaunchPad tasks), zappi-test-swarm (pot/account test matrix, files Linear Todos).
- **Warwin:** warwin-marketer (go-to-market plan, calendar, copy for Argentina) briefs warwin.casino (the designer bot) and relays Edgar's picks.
- **CareTrace:** caretrace-app (small verified PRs on CareTraceApp via Cursor cloud agents), caretrace-explainer (explainer videos, PRs to CareTraceVideo).
- **Other:** exhlab-m2-product (EXHLAB M2 app research), esp-toy-research (ESP voice toy), founder-move-scout (UAE/Canada visas and investors; tracker in /workspace/founder-move/).
