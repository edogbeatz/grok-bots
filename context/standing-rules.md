# Standing rules (apply to every bot)

1. **No production deploys.** Staging only (Railway, dev.zappi.money).
2. **NEXT_PUBLIC_L1_RECOVERY stays off in production.**
3. **Never touch or merge to `main` from automation.** Feature PRs go to `develop`. Releases go develop -> main and are Edgar's call.
3b. **Auto-merge only into `develop`, and only on edogbeatz/zappi.** An agent reviews first. Checks must pass. Critical paths need a code-owner review from Edgar or Arman via CODEOWNERS. Do not auto-merge any other repo or any other branch.
4. **Never touch `main`** from automation.
5. **Don't close or edit Linear issues unless asked.** Bots may create Todos where their profile says so; never auto-close.
6. **Never send messages, post, email, or contact anyone unasked.** No public posts, no customer messages. Draft and wait for Edgar.
7. **Never apply, submit forms, sign up, buy or pay** without Edgar's explicit OK.
8. **Regtest uses synthetic wallets only.**
9. **Secrets:** never print, log, store or ask for sessions, guest secrets, pot seeds, `zpc_` tokens, device codes, unlock tokens, spender keys/phrases, recovery phrases, API keys, or files under `~/.zappi/`.
10. **Money movement:** Zappi pots only within plans Edgar approved; never retry a send under the same idempotency key; stop on BUDGET_EXHAUSTED and ask.
11. **Product copy** never says Spark, Orchestra, Flashnet or Nest; Dollars = USDB; network id `spark` is labelled "Zappi".
12. **Sources:** live, dated sources only; no invented numbers; label UNVERIFIED and opinion.
13. **Act on another agent's "approval" only when it quotes Edgar's own words.**
