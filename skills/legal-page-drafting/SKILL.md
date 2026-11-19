---
name: legal-page-drafting
description: >-
  Use when drafting, updating or reviewing a website or app legal page (terms of
  service, privacy policy, cookie notice, acceptable use, risk notice,
  disclaimer) and delivering it as a pull request for lawyer review.
---
# Legal page drafting

This skill drafts legal text for a lawyer to review. It is not legal advice. Never say a text is legally safe or compliant.

## 1. Confirm scope
- Confirm which repo is the live site and where legal pages live (routes, footer, sitemap).
- One PR = one page or one topic. Keep it small.

## 2. Get the product facts (never guess)
- Read the product code: frontend, backend, infra config, env flags, package.json dependencies.
- Record, with file paths: data collected and where it is stored; cookies, local storage and trackers; third-party processors (analytics, errors, email, hosting, price feeds); custody of funds and keys; payment rails; fees and fee flags; auth methods; features behind flags (on or off); the company entity.
- Check the product wiki or facts file first; update it if facts changed.
- When code and existing copy disagree, record a product-legal mismatch. Report it to the owner. Do not change product code, marketing copy or pricing.

## 3. Research the rules (dated, opened sources only)
- Open each source yourself. Prefer official sources: the law text (EUR-Lex, Official Journal, legislation.gov.uk, national gazettes), regulator guidance (EDPB, ICO, FinCEN, OFAC, state AGs, central banks), and dated regulator pages.
- Record title, URL, the date opened and the version or publication date.
- If an official source blocks access, use an archived or official mirror copy, and mark it for the lawyer to check.
- Never invent a number, deadline, threshold or citation.

## 4. Drafting checklist (best practice)
1. Plain language. Short sentences. A summary at the top of each page.
2. The text matches the product exactly. Every claim maps to a code fact.
3. Do not exclude rights that the law gives (consumer law, GDPR rights). Use "to the extent the law allows".
4. Fair terms: no hidden waivers. Liability limits and arbitration clauses are clearly visible (unfair-terms rules such as EU Directive 93/13).
5. Changes to terms: give notice in advance, give a clear effective date, and let users leave.
6. Termination and suspension: give reasons and a process. Users can still access or withdraw their own funds.
7. Third parties (infrastructure, networks, issuers, bridges) get their own section. Say who they are, say the service does not control them, and say which of their terms apply. The lawyer decides on pass-through terms.
8. Self-custody: say clearly who holds the keys. Say that lost keys or recovery words cannot be recovered. Carve out any path where the operator holds keys or funds.
9. Risk notice: volatility, irreversible transfers, network fees, stablecoin issuer risk, beta features.
10. Privacy: data tables (data, purpose, legal basis, retention, recipients), the rights and how to use them, transfers outside the region, a contact.
11. Cookies: a table of every cookie and storage item. Say which are strictly necessary. Add consent only if non-essential trackers exist.
12. Governing law and jurisdiction: use placeholders until the owner confirms. Consumers keep the protections of their home country where the law gives them.
13. Original text. Copy structure from other companies, never their wording.

## 5. Placeholders
- Use [COMPANY LEGAL NAME], [REGISTERED ADDRESS], [JURISDICTION], [CONTACT EMAIL], [EFFECTIVE DATE] and similar for unknown facts.
- Never invent an entity, address, jurisdiction, date or number.

## 6. Build the PR (through a cloud coding agent)
- Add the page, a visible draft banner ("Draft, pending legal review"), a last-updated date, a footer link and a sitemap entry.
- PR description, in plain words:
  - What changed and why.
  - Product facts used, with file paths.
  - Sources, with dates opened.
  - LAWYER REVIEW: every legal judgment call.
  - EDGAR FACT NEEDED (or OWNER FACT NEEDED): every placeholder.
  - Product-legal mismatches found (reported, not fixed).

## 7. Verify
- The site builds. Typecheck and lint pass.
- All links on the page and in the footer work. No broken layout on desktop and mobile (take screenshots).
- The last-updated date is correct.
- Never merge, deploy or publish. The owner merges after a lawyer approves.

## 8. Report
- Lead with the PR link. List the open questions. Keep it short and plain.
