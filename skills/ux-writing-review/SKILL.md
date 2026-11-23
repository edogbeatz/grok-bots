---
name: ux-writing-review
description: >-
  Use when judging the on-screen copy of a live web or mobile app (buttons,
  errors, empty states, forms, confirmations, loading, onboarding) during a UI
  review. Adds copy checks to a Pass/Friction/Broken rubric; does not replace
  it.
---
# UX writing review (live UI copy)

Source: https://github.com/content-designer/ux-writing-skill (MIT) @ 98cacde4ba2dd10ed28df43a8d53eef1e321c539, SKILL.md sha256 67dda2a5ba7e26f69860e1018a37068ca201735ff8ae98199c143138d91b4550. Pinned copy on the shared box: /workspace/vendor-skills/ux-writing-skill/ (provenance in SOURCE.txt). Supplement: anthropics/knowledge-work-plugins design/skills/ux-copy (Apache-2.0). Adapted from a drafting skill to judging live on-screen copy.

## How to use
- Run next to your existing rubric. Keep Pass / Friction / Broken per flow. A copy miss is Friction; it is Broken only if the user cannot finish the task (for example, an error with no way forward).
- Judge only text you can see on screen. Quote it exactly.
- Apply any product-specific copy rules from your own brief or memory first (banned words, product names, unit labels, brevity preferences).
- Finding format: URL + element + rule + exact on-screen text + suggested rewrite + screenshot + viewport + time. Never file:line.
- Sentence-length figures in the source (for example "8 words = 100% comprehension") are UNVERIFIED; do not cite them as facts.

## Four standards (score each screen)
- Purposeful: every line has a job; helper text does not repeat the title or the button; nothing said twice.
- Concise: shortest wording that keeps meaning; front-load the useful fact.
- Conversational: plain language, active voice, second person, no jargon, idioms or internal system names.
- Clear: one meaning; literal; consistent terms.

## Checks
- Case: one consistent case style for titles, buttons and labels (sentence case unless the product's style says otherwise).
- Buttons and links: specific verb + object that matches the outcome ("Send $1", "Create invoice"). Flag generic OK, Submit, Click here, Learn more with no object, and Continue where the consequence matters.
- Errors: say what failed, why if known, and what to do next. No blame ("invalid", "illegal", "you entered the wrong"). No bare codes. No "Something went wrong" without a recovery step. A disabled primary button with no message explaining why is a miss.
- Success: short, specific, past tense ("Sent to <name>", "Changes saved").
- Empty states: say why it is empty and give a next action. A dead-end empty state fails.
- Confirmations: name the action and its consequence; action buttons use the verb, not only OK/Cancel. Money and destructive actions state amount and target.
- Consistent terms for the same thing across screens (send vs withdraw, sign in vs log in, invoice vs address).
- Status in words, not color or an icon alone.
- Fields: visible labels; placeholders are examples, never the only label.
- Link text names the destination.
- Inclusive, literal language: no idioms, no gendered defaults, no humor in errors, payments or loss-of-funds states.
- Loading copy sets an expectation ("Sending…"), with an ellipsis character.
- Times, dates and amounts are readable and consistent; times show the right zone.
- Numerals for counts and amounts.

## Note only, needs code or assistive-tech check
- Errors programmatically tied to fields, ARIA names on icon-only controls, screen-reader announcements, contrast ratios, text expansion for translation.
