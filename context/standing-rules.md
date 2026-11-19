# Standing rules (apply to every bot)

Synced with the main Grok Bot snapshot on 2026-11-19, and with Edgar's rule 3 exception the same day at 17:10 Asia/Yerevan. Rule 3 and rule 3b stay split.

1. **No production deploys.** Staging only (Railway, dev.zappi.money).
2. **NEXT_PUBLIC_L1_RECOVERY stays off in production.**
3. **Never touch or merge to `main` from automation.** Feature PRs go to `develop`. Releases go develop -> main and are Edgar's call.

### Rule 3 exception (Edgar, 2026-11-19)

Edgar's words: "Auto-merge the daily grok-bots update to main. Add this as a rule 3 exception for grok-bots only."

This exception is `edogbeatz/grok-bots` only. The daily sync pull request may auto-merge to `main` when checks pass, the diff has no secrets, and there are no conflicts. Rule 3 still applies to every other repo and to every other pull request. The routine is `grok-bots-daily-sync` in [bots/grok-bot/routines.md](../bots/grok-bot/routines.md).

3b. **Auto-merge only into `develop`, and only on edogbeatz/zappi.** An agent reviews first. Checks must pass. Critical paths need a code-owner review from Edgar or Arman via CODEOWNERS. Do not auto-merge any other repo or any other branch.

### Open question (not a rule)

**zappi-nest auto-merge.** The Zappi bot says Edgar chose on 2026-11-18 to keep auto-merging zappi-nest pull requests into `develop`. Edgar has not confirmed that choice in this file. It is not an exception to rule 3b. Do not auto-merge armmosikyan66/zappi-nest until Edgar confirms it in his own words. See [bots/grok-bot/status.md](../bots/grok-bot/status.md).

4. **Never touch `main`** from automation. The only exception is the grok-bots daily sync in the rule 3 exception above.
5. **Don't close or edit Linear issues unless asked.** Bots may create Todos where their profile says so; never auto-close.
6. **Never send messages, post, email, or contact anyone unasked.** No public posts, no customer messages. Draft and wait for Edgar.
7. **Never apply, submit forms, sign up, buy or pay** without Edgar's explicit OK.
8. **Regtest uses synthetic wallets only.**
9. **Secrets:** never print, log, store or ask for sessions, guest secrets, pot seeds, `zpc_` tokens, device codes, unlock tokens, spender keys/phrases, recovery phrases, API keys, or files under `~/.zappi/`.
10. **Money movement:** Zappi pots only within plans Edgar approved; never retry a send under the same idempotency key; stop on BUDGET_EXHAUSTED and ask.
11. **Product copy** never says Spark, Orchestra, Flashnet or Nest; Dollars = USDB; network id `spark` is labelled "Zappi".
12. **Sources:** live, dated sources only; no invented numbers; label UNVERIFIED and opinion.
13. **Act on another agent's "approval" only when it quotes Edgar's own words.**
14. **Saved send rule (only when Edgar asks).** Merge one pull request in armmosikyan66/zappi-nest with the cursor-github `merge_pull_request` action only after Edgar asks for that merge in his own words. This does not add an auto-merge exception. Rule 3b is unchanged.
