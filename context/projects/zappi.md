# Zappi

- Wallet for Bitcoin and Dollars (USDB on Spark). 12 recovery words are made in the browser. Web app is headless on Flashnet Orchestra; **Nest** (armmosikyan66/zappi-nest, owner Arman) owns Flashnet/Orchestra SDK calls and the catalog. The browser signs Spark.
- **Pots:** prepaid wallets funded for AI agents; agents connect via the remote MCP server (or zappi-cli) and spend only what's in the pot, with passkey approval or allowance. Sellers can charge agents through an HTTP 402 paywall (x402 / L402 story).
- **Repos:** edogbeatz/zappi (web; feature PRs -> `develop`, releases develop -> `main`), zappi-nest, zappi-sdk (Arman merges/tags), zappi-cli, zappi-pot skill (served at dev.zappi.money/pots/SKILL.md).
- **Staging:** Railway, https://dev.zappi.money. No prod deploys by bots.
- **Marketing source of truth:** the zappi repo `wiki/marketing/` (the old "Zappi Marketing Brain" repo is only a pointer).
- **Linear:** skribz workspace, team LaunchPad, project Zappi; initiatives Zappi Wallet & Platform, Zappi SDK, Marketplace Integrations; project Zappi Agent Tools.
- **PR policy (Edgar, 2026-11-10):** agents review and auto-merge into develop; CODEOWNERS require Edgar or Arman on critical paths (keys/wallet, auth/passkeys, payments, pots/refunds, migrations, secrets, CI gates). Overlap check treats wiki/log.md and wiki/index.md edits as non-blocking.
- **Open as of 2026-11-16:** epic 1-1095 Deposit & Withdraw Flows performance; Nest priority list (1-1083, 1-860, 1-915, 1-1076, lint debt, 1-1019 ...); web PRs #562-#564; potrin4t5 deposit unfinished; L1 recovery flag off.
- **Bots:** Zappi, Zappi rail review, zappi-test-swarm, zappi-researcher, zappi-competitor-watch, zappi-product-marketer, zappi-content, zappi-site-audit, zappi-explainer-animation.
