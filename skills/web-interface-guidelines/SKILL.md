---
name: web-interface-guidelines
description: >-
  Use when judging a live web app UI in the browser (not source code) against
  Vercel's Web Interface Guidelines: accessibility, focus, forms, motion,
  typography, content, layout, touch, dark mode, i18n, copy. Adds to a
  Pass/Friction/Broken UX rubric; does not replace it.
---
# Web Interface Guidelines (live UI review)

Source: https://github.com/vercel-labs/web-interface-guidelines @ 434b7f9, command.md sha256 d246b026f4f29b5823a9cc857f9edf3d2507002e055e32040cadeaf3b38e0234 (pinned copy on the shared box: /workspace/vendor-skills/web-interface-guidelines/command.md). Adapted from a code review to a live, in-browser review.

## How to use
- Run it as an extra layer next to your existing rubric. Keep Pass / Friction / Broken scoring per flow. A guideline miss raises a flow to Friction, or to Broken only if it blocks the task.
- Test only what you can see or try on the page: what the screen shows, DOM/inspect (elements panel, computed styles, page source), keyboard tab-through, a ~390 px phone-width window, prefers-reduced-motion and dark mode (devtools emulation or OS/app theme), and on-screen copy.
- Rules marked (code) cannot be proven from the page. Note them only as "note only, needs code check" when you see a symptom; never claim them as findings.
- Finding format: URL + element (visible label or selector) + rule + what you saw (exact on-screen text) + screenshot + viewport + time. Never file:line.
- No secrets, codes, keys or full addresses in screenshots; crop or redact.

## Checks

### Accessibility
- Icon-only buttons have an accessible name (inspect aria-label).
- Form fields have a visible label or aria-label.
- Actions are buttons, navigation is links (inspect: no clickable div/span; links open with Ctrl/Cmd+click and middle-click).
- Images have alt (alt="" if decorative); decorative icons aria-hidden.
- Async updates (toasts, validation) are announced: aria-live region present.
- Heading order makes sense (h1 then h2...); a skip-to-content link exists.
- Media has captions or text; media controls work by keyboard.
- Keyboard handlers on custom widgets: tab to it, Enter/Space works.

### Focus
- Every interactive element shows a visible focus ring on Tab.
- No focus ring on mouse click (focus-visible behavior).
- Sticky header, footer or overlay never covers the focused element.
- Dialogs: focus moves into the dialog, stays there, returns on close; Esc closes.

### Forms
- Correct input type and keyboard (email, number, tel, url) on phone width.
- Paste works in every field (try pasting into codes, amounts, addresses).
- Clicking a label focuses its field; checkbox/radio label is part of the hit target.
- Spellcheck off on emails, codes, usernames, addresses (no red squiggles).
- Submit stays enabled until the request starts, then shows a spinner; no double submit.
- Errors show inline next to the field; on submit, focus goes to the first error.
- Disabled buttons explain why (or the field shows the reason).
- Placeholders show an example and end with an ellipsis.
- Leaving a form with unsaved changes warns first.
- Inputs have sensible autocomplete (password managers trigger only on auth fields).

### Animation
- With reduced motion on, motion is reduced or off; decorative loops stop.
- Animations do not block input; you can act mid-animation.
- Autoplay motion over 5 s has pause/stop/hide.
- (code) animate transform/opacity only; no transition: all; transform-origin. Note only.

### Typography
- Ellipsis character, not three dots; loading text ends with it ("Loading…").
- Curly quotes in copy.
- Units and brand names do not break across lines.
- Number columns align (tabular numbers) in lists of amounts.
- Headings have no single-word last line where avoidable.

### Content handling
- Long names, amounts, addresses truncate or wrap; no overflow at 390 px.
- Empty states are designed (no blank or broken UI for zero items).
- Try very short and very long user input (names, notes).

### Images
- No layout shift when images load (watch on reload).
- (code) explicit width/height, lazy loading, fetchpriority. Note only, check in inspect if easy.

### Performance (as felt)
- Long lists scroll smoothly; typing in fields has no lag.
- No visible font swap flash or late layout jump.
- (code) virtualization, layout reads in render, preconnect, font preload. Note only.

### Navigation and state
- URL reflects state: tabs, filters, open panels, pagination survive reload and can be shared.
- Back button returns to the previous step, not out of the app.
- Destructive actions need a confirm or an undo window.

### Touch and interaction (390 px)
- Tap targets at least about 44 px; no double-tap zoom delay.
- Modals and sheets do not scroll the page behind them.
- Gestures (swipe, drag) also have a tap/click and keyboard way.
- Fields do not autofocus on phone width unless it is the single primary input.

### Safe areas and layout
- No horizontal scrollbar at 390 px or desktop.
- Full-bleed content respects notches (check in phone emulation).

### Dark mode and theming
- Dark mode: scrollbars, inputs and native selects match the theme; no white flashes.
- Theme color of the browser bar matches the page (inspect meta theme-color).

### Locale and i18n
- Dates, times and numbers formatted for the locale; times show in the user's zone.
- Brand names and identifiers are not garbled by browser translation (translate="no").

### Hydration (code)
- Symptoms only: content flicker or a field that resets right after load. Note only, needs code check.

### Hover and states
- Buttons and links show hover feedback; hover/active/focus are more visible than rest.

### Content and copy
- Active voice, second person, no first person.
- Specific button labels ("Send $1", not "Continue" where a specific label fits).
- Error messages say how to fix it, not just what failed.
- Numerals for counts.
- Title Case for headings and buttons only if the product's style uses it; otherwise note only.

### Anti-patterns to flag (visible from the page)
- Zoom disabled (inspect viewport meta for user-scalable=no / maximum-scale=1).
- Paste blocked.
- No visible focus ring.
- Clickable div/span instead of button/link.
- Fields without labels; icon buttons without names.
- Hardcoded or wrong date/number formats.
- Unjustified autofocus.
- Animated GIF where a video fits.
- Gesture-only action.
