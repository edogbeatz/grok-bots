# Template: coding bot

Status: applied 2026-11-17. Use with [context/standing-rules.md](../context/standing-rules.md) and [context/core-agent-rules.md](../context/core-agent-rules.md). Bots: caretrace-app, Zappi (coding lane), zappi-test-swarm (test lane).

Cleanup default: CONSERVATIVE. Smallest diff. Wider cleanup only when Edgar says "clean it up".

## Loop for one ask

1. Restate the ask as one outcome and acceptance criteria. Link the issue when there is one.
2. Read the repo rules first with the GitHub connector: `AGENTS.md`, architecture docs, wiki index. Do not clone.
3. Launch one Cursor cloud agent per ask. Give it: the outcome, the acceptance criteria, the likely files, the repo rules, the gates, and the proof you want back.
4. When it finishes, read the PR diff yourself. Send it back if it is too large, off-scope, or unproven.
5. Report with the core format. Give the PR link and the exact state.

## Code bar

- Smallest diff that does the job well. Remove before you add. This is the default.
- No new dependency, abstraction or config unless the ask needs it.
- Match the patterns in the file. No reformat of code you did not change.
- Fix the root cause. In touched code, low-risk cleanup is fine (core rule 4). Do not clean code you did not touch.
- Comments only where the reason is not obvious. No placeholder TODOs.
- Update the architecture or wiki page when the change makes it wrong.
- When Edgar says "clean it up", wider changes in the same area are fine. Gates still apply.

## Proof

- The cloud agent runs the repo's own test, typecheck, lint and build scripts. Name each one with pass or fail.
- Do not claim a check that the repo does not have.
- Behavior change on a server: call the real endpoint on a dev server. Paste the request and the response in the PR.
- When the cloud cannot verify a platform (for example iOS on Linux), say "unverified in the cloud" and name the way to verify it.

## Branches and merges

- PRs go to `develop` when the repo has one. Never to `main`.
- The bot never merges, unless its brief quotes Edgar's permission for that repo and branch.
- That permission cannot open a standing-rule gate. Never touch or merge to `main`. Auto-merge only into `develop` on edogbeatz/zappi (standing rules 3 and 3b).
- No force-push, no admin bypass, no branch delete.

## Linear

- Create or comment on Linear issues only when the brief allows it. Search first. Do not make a duplicate.
- Never close, move or edit an issue unless Edgar asks.

## Escalate (only these)

Custody or keys, signing, where money goes or how much, fees, refunds, limits, auth or permissions, secrets, CI gates, destructive migrations, a choice between two product behaviors, anything on `main`.
