# Memory: Zappi rail review

Durable facts as seen in this bot's memory context and its UpdateMemory writes. The transcript tool cut long memory blocks in the middle, so this list can be incomplete; marked where cut. Shared user facts are in `context/user.md`, not repeated here.

About the user (profile):
- (learned 2026-11-09) Edgar wants a daily weekday watch (around 10:00 Yerevan time; Monday also covering the weekend) on Orchestra, Flashnet (github.com/flashnetxyz), Spark, and Lightspark Grid, reported as what changed and how it affects Zappi's fees, routes, limits, deposits and refunds, and silent when nothing changed.
- (learned 2026-11-06) Edgar's Zappi pot "chocho-2" has no spending limit, so every payment from it returns an approve link for confirmation.
- (learned 2026-11-06) Edgar's chocho account has pot "chocho-2" (id 3c32a6bf-7b87-4ad8-8543-d926f7eef8ba).
- (learned 2026-11-05) When a pot allowance is exhausted (BUDGET_EXHAUSTED) or too small for the planned sends, stop and ask Edgar to add allowance, with a link to that pot's page on dev.zappi.money, the amount needed (remaining plan gross plus fees) and which rail to resume from.
- (learned 2026-11-05) Mode 3 send plan (Edgar, 2026-11-05): before each test send, quote gross, network fee shown, fee quoted and expected net; read the source balance and remaining allowance, counting pending_recovery/reserved as spent; refuse or resize if gross exceeds the loaded balance after fees or the remaining allowance; on BUDGET_EXHAUSTED or pending_recovery stop and report, never resend; record rail, gross, fee shown/quoted/deducted, net, status timeline, txid.
- (learned 2026-11-05) Edgar wants Zappi pots to receive Bitcoin on L1 and Lightning (converting to USDB/Dollars) the same way the main wallet does.
- (learned 2026-11-05) As of 2026-11-05, Edgar is depositing about $12 into chocho so the assistant can use pot chocho-1 for continuing tests of the remaining networks and rails (sending to dlo-1).
- (learned 2026-11-...s into small, verified pull requests, shipped through Cursor cloud 
- exhlab-m2-product (id: 72de6273-d4bb-40e3-b867-7b992bb7064f): My only job: help Edgar develop an app based on EXHLAB's M2 equation by researching competition, understanding the targe
- zappi-researcher (id: 760e4db4-5614-4b56-84b7-371820abd898): My only job: a weekly market brief for Zappi's agent-payments story. Each Monday I check what changed in the last 7 days
- zappi-product-marketer (id: 805dc36a-1e88-4a40-bc8c-e91bb413a849): My only job: own Zappi's positioning and turn it into copy drafts. I keep the Zappi Marketing Brain true and current, an
- zappi-explainer-animation (id: 919c79bc-2513-42c5-88af-69ff3f364771)
- Grok Bot (id: 9bce498a-82dd-46ba-a2a8-4c9e2248c738): A teammate with its own computer that takes real work off your plate.
- zappi-competitor-watch (id: 9f21027b-840f-49e2-9f8e-2e84444b3ca3): My only job: watch Zappi's competitors and report who is building what in agentic and crypto-first payments. I report in
- zappi-content (id: ba54d60d-ebf7-4316-98a3-75ddd87244d4): My only job: draft Zappi's owned content for the agent-payments path, meaning docs intros and demo walkthrough scripts, 
- Zappi (id: cdff0cfc-2ade-47d9-b08b-68132696d5ae)
- caretrace-explainer (id: e3ce860d-498a-473a-bce2-3da276673781): My only job: make short CareTrace explainer videos from code. Each video is an HTML/GSAP scene that I render frame by fr
- founder-move-scout (id: e89eb0e7-fe7c-48e6-b6af-d1088662ee50): My only job: research investors and visa or residency routes in the UAE and Canada for Edgar's two startups, CareTrace (
- esp-toy-research (id: fd1b4b42-7333-43e2-93ce-37eb34574c44): My only job: research for Edgar's ESP-based personal-assistant toy (kids and adults). I report findings with dated sourc
- zappi-test-swarm (id: fe1ea36f-e6d6-4ca9-9010-cbaf12930b50): My only job: orchestrate Zappi pot and account tests across internal and external rails, then turn every real failure in
</teammates>

_(memory block was truncated in the middle by the transcript reader; remaining facts unknown, recover from the bot's memory)_

## Memory writes seen in recent history

- (journal) 2026-11-15 23:06 Yerevan: at Edgar's request, squash-merged docs PR edogbeatz/zappi#544 into develop (merge commit 14f76a6); CI was skipped because of the Actions billing block; not on main, not deployed.
- (journal) 2026-11-16: at Edgar's direct request ("create it yourself") I filed Linear 1-1076 (Nest: Orchestra Tron refundAddress validation and new 503 retry codes), LaunchPad, assigned to Arman Mosikyan, under epic 1-1042, and told @Zappi not to file it again.
- (profile) Since 2026-11-16 Edgar wants the daily rail watch to file High-priority LaunchPad Linear tasks for noticeable issues: backend (Nest) to Arman Mosikyan, frontend (web) to Edgar, one linked task per layer when both, skipping duplicates.
