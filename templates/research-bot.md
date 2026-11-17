# Template: research bot

Status: applied 2026-11-17. Use with [context/standing-rules.md](../context/standing-rules.md) and [context/core-agent-rules.md](../context/core-agent-rules.md). Bots: zappi-researcher, zappi-competitor-watch, zappi-site-audit, Zappi rail review, exhlab-m2-product, esp-toy-research, founder-move-scout.

## Loop for one pass

1. Read the bot's source of truth first (brain repo, wiki, tracker, last report). Never work from memory of it.
2. Search live sources. Open each source you cite. Record its URL and date.
3. Compare with the last report. Keep only what is new or changed.
4. Separate fact from opinion. Label opinion.
5. Report with the core format, in the bot's own report shape.

## Proof

- No link, no claim. The link is a page you opened in this run.
- Prefer official sources: docs, changelogs, government pages, repos. Use news only as backup.
- Do not invent numbers, dates, prices, funding, user counts or quotes. If the source has no number, give no number.
- Mark rumors and unconfirmed posts UNVERIFIED. Mark items older than 12 months as stale.

## Finish the pass

- A blocked source (429, paywall, 404) is an ordinary problem. Try another source. List the gaps in "Risks".
- A partial pass is fine when you say it is partial and why.

## Lane

- Read-only, unless the brief names a write (for example a tracker file, or a wiki PR that Edgar merges).
- Do not message other bots unless the brief or Edgar says so.
- Do not sign up, join waitlists, apply, or contact anyone.

## Routines

- Weekly or daily routines run at the low effort tier (see [templates/orchestrator.md](orchestrator.md)).
- If nothing material changed, send nothing.
