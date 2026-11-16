# Routines: Zappi

Recovered from the bot's routine tool calls (UpdateRoutine create/update/get/pause) in its chat history. Times are Asia/Yerevan. Recreate each with UpdateRoutine `action: create` from inside the new bot.

## Watch PR #464 (develop test fix)

- **Folder/id:** `watch-pr-464-develop-test-fix`
- **State:** paused
- **Trigger:** `{"type": "github", "repo": "edogbeatz/zappi", "pr": 464, "events": ["pr-merged", "pr-closed", "ci-failed"]}`
- **Server summary:** When a PR merges, a PR closes, or CI fails in edogbeatz/zappi on PR #464.

**Saved prompt:**

````text
Watching edogbeatz/zappi PR #464, which fixes two stale tests on develop and has squash auto-merge queued into develop.
- If it merged: tell Edgar it merged into develop. Then update PR #447's branch with GitHub's "update branch" on the source-control tools, so its checks run again on the fixed develop. #447 already has squash auto-merge queued into develop. Do nothing else to #447: no merge, no admin. Say the branch was updated, or say why the update failed.
- If it closed without merging: tell Edgar.
- If CI failed: tell Edgar which check failed and the failing step or test, in a sentence or two. Don't fix anything.
Results go to Edgar in this Grok Bot chat. Never touch main.
````

## Watch PR #447 auto-merge

- **Folder/id:** `watch-pr-447-auto-merge`
- **State:** paused
- **Trigger:** `{"type": "github", "repo": "edogbeatz/zappi", "pr": 447, "events": ["pr-merged", "pr-closed", "ci-failed"]}`
- **Server summary:** When a PR merges, a PR closes, or CI fails in edogbeatz/zappi on PR #447.

**Saved prompt:**

````text
Watching edogbeatz/zappi PR #447, which has squash auto-merge queued into develop.
- If it merged: tell Edgar it auto-merged into develop, and check whether its head branch was deleted automatically.
- If it closed without merging: tell Edgar.
- If CI failed: tell Edgar which check failed and why, in a sentence or two. Stay quiet if the failure is the old pre-fix result still showing, from before PR #464 merged and the branch was updated. Don't fix anything.
Results go to Edgar in this Grok Bot chat. Never touch main.
````

## Zappi develop PR auto-fixer

- **Folder/id:** `zappi-develop-pr-auto-fixer`
- **State:** paused
- **Trigger:** `{"type": "group", "listeners": [{"type": "github", "repo": "edogbeatz/zappi", "events": ["pr-opened"]}, {"type": "cron", "schedule": "0 9-23/2 * * *"}]}`
- **Trigger as stored:** `trigger: {"type":"group","listeners":[{"type":"cron","schedule":"CRON_TZ=Asia/Yerevan 0 9-23/2 * * *","firesAt":"CRON_TZ=Asia/Yerevan 7 9-23/2 * * *","window":{"earlyMinutes":15,"lateMinutes":15},"timing":"flexible"},{"type":"github","repo":"edogbeatz/zappi","events":["pr-opened"]}]}`
- **Server summary:** Every 2 hours, 9:00 AM – 11:00 PM (may run up to 15 min early or 15 min late) or when a PR opens in edogbeatz/zappi, next run 11/10/2026, 1:07:00 PM GMT+4.

**Saved prompt:**

````text
Keep agent PRs into `develop` on edogbeatz/zappi flowing to auto-merge. Edgar (Nov 10): "auto merge after reviewing because agent is reviewing in the end. if something is stuck only in that case let me know." So agents review and merge everything into develop, including critical code; Edgar hears only about stuck items.

Each run:
1. List open PRs in edogbeatz/zappi whose base is `develop` (ignore PRs targeting `main`; never touch or merge into `main`). Include drafts. For each, look at mergeability, the `Checks` status check and its failing step, draft state, review requirements, and whether squash auto-merge is enabled.
2. Handle yourself:
   - Mechanical: merge conflicts (keep both sides' intent, lint/typecheck/tests pass), branch behind develop, lint/format/typecheck errors, stale or flaky tests, overlap failures, Dependabot PRs (recreate from develop when cut from main; minor/patch bumps; leave major bumps needing a real migration alone quietly), missing squash auto-merge on a green PR, CI re-runs.
   - Bugbot/security-agent drafts: have a cloud agent confirm the bug is real, the fix minimal and tested, CI green; then mark ready and enable squash auto-merge. If not real or already fixed, close with a short comment.
   - Critical PRs (custody/keys, signing, where money goes or how much, refunds, fees, limits, auth/permissions, secrets, CI gates, migrations): don't hold them for Edgar. Have a cloud agent do a careful review: verify the change is correct and safe, matches the PR's stated intent, doesn't send funds to a wrong or attacker-controlled destination, doesn't bypass auth, leak secrets, weaken gates without reason, or destroy data, and that tests cover it. If the review passes, enable squash auto-merge and post a short review summary comment on the PR. If the review finds a fixable problem, fix it on the branch and then merge. If it finds a real bug or unsafe behavior with no clear fix, or it requires choosing between two different product behaviors, that is "stuck".
   - For each fix, first check (find by PR) whether a cloud agent is already on it; if so, leave it. Otherwise launch a cloud agent on https://github.com/edogbeatz/zappi from the PR's branch (batch PRs when simpler). Rules: merge develop, no rebase, no force push, never admin bypass, never merge manually, keep squash auto-merge on.
3. Stuck = something an agent can't finish: a required code-owner review that no agent can give (e.g. PR authored as edogbeatz needing Arman, or Edgar for others), an unsafe change with no clear fix, a behavior choice, repeated CI failures an agent couldn't fix, a GitHub permission an agent lacks (e.g. Dependabot recreate), or anything touching `main`.
4. Message Edgar in this Grok Bot chat only about new stuck items, with a link and one plain sentence on what's needed from him. Don't repeat items already reported unless they changed. Don't report reviews, fixes or merges. If nothing new is stuck, send nothing.
````

## Watch PR #467 overlap allowlist

- **Folder/id:** `watch-pr-467-overlap-allowlist`
- **State:** paused
- **Trigger:** `{"type": "github", "repo": "edogbeatz/zappi", "pr": 467, "events": ["pr-merged", "pr-closed", "ci-failed"]}`
- **Server summary:** When a PR merges, a PR closes, or CI fails in edogbeatz/zappi on PR #467.

**Saved prompt:**

````text
PR #467 on edogbeatz/zappi (overlap check ignores wiki/log.md and wiki/index.md), targeting develop with squash auto-merge, was approved by Edgar. Cloud agent bc-e62740f1-0029-5ef6-9fda-cd09f0075af2 ("Unstick develop PRs") already owns updating #449, #450, #453, #461, #462 and the other develop PRs after #467 lands, so do NOT start another agent for those.
- If it merged: tell Edgar in this Grok Bot chat in one sentence that #467 merged and the stuck PRs are being updated now.
- If CI failed: if it's mechanical (lint, test, typecheck in its own change), reply to cloud agent bc-91968b63-39c1-56fb-9053-c13b2166e233 (which made #467) to fix it on the same branch; otherwise tell Edgar in this chat what failed.
- If closed without merging: tell Edgar in this chat.
````

## Watch PR #468 overlap warning gate

- **Folder/id:** `watch-pr-468-overlap-warning-gate`
- **State:** paused
- **Trigger:** `{"type": "github", "repo": "edogbeatz/zappi", "pr": 468, "events": ["pr-merged", "pr-closed", "ci-failed"]}`
- **Server summary:** When a PR merges, a PR closes, or CI fails in edogbeatz/zappi on PR #468.

**Saved prompt:**

````text
PR #468 on edogbeatz/zappi (overlap check becomes a warning when the PR is up to date with develop and merges cleanly) targets develop with squash auto-merge, approved by Edgar. Cloud agent bc-9eaea0b2-1d5a-5ab8-9580-b63a4193a968 made it.
- If it merged: reply (queue) to that cloud agent to do its promised follow-up now: merge latest develop into #461, #453, #450, #449, #459, #455, #440 (no rebase, no force push, no admin bypass), keep both sides of wiki conflicts, run lint/typecheck/tests, push, make sure Checks re-runs, enable squash auto-merge on #459, #455, #440 unless they change custody/keys, where money goes or how much, or auth; keep updating the remaining ones as develop moves until all merge or hit a real blocker; don't touch #444, #427, #465, drafts or main. Send Edgar nothing at this step.
- If CI failed: if mechanical, reply to that agent to fix it on the same branch and send Edgar nothing; if not mechanical, tell Edgar in this Grok Bot chat what failed in one or two sentences.
- If closed without merging: tell Edgar in this chat.
````

Note: on 2026-11-15/16 Edgar asked to stop token use; all five routines were paused (not deleted). The four PR watchers are for PRs that already merged, so they can be skipped on a new account. Recreate the PR auto-fixer paused unless Edgar says to resume it.
