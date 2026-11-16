---
name: poster-typography
description: >-
  Use when designing or reviewing poster, social-graphic, cover, Story or banner
  typography — hierarchy, spacing, contrast over photos, Spanish type,
  offers/numerals, and a final QA pass.
---
# Poster and social-graphic typography

Instructions for designers and design bots. Prefer brand constants over these rules when they conflict; flag the conflict, do not silently override the brand. Numbers cited to a source are requirements; ranges marked **working default** are practical starting points, not facts. Full source list: `/workspace/warwin/research/poster-typography-sources.md` (accessed 2026-11-09).

## Steps

1. Load brand type constants first (fonts, sizes, colours, safe zones, legal band).
2. Lock a max-3-level hierarchy and write the hierarchy map before placing type.
3. Set display first (headline / offer), then subhead, then body/legal — never the reverse.
4. Space: track large display tighter, open all-caps small text, set leading optically, kern the headline.
5. Place type on the grid with safe margins; keep negative space; never cross faces or UI chrome.
6. Prove contrast on the actual photo (scrim/gradient if needed); run the thumbnail and distance tests.
7. Apply Spanish rules (glyphs, ¿¡, sentence case, length room, hyphenation).
8. Set legal/disclaimer at compliant size; run the QA checklist before export.

## 1. Hierarchy (max 3 levels)

- Cap visual hierarchy at **three levels** (headline → support → detail). Two is better when possible. Source: Butterick, *Headings*; Baumann poster guide (max three type sizes).
- On posters/social, make steps obvious: **working default** ~**1.5–2×** between adjacent levels (Material's UI major-second 1.125 is too subtle for posters). Source for modular scales: Material Design 3; larger poster jumps are a **working default**.
- Hierarchy cues: size, weight, colour, placement — not underline, not random fonts. Source: Lupton / Butterick.
- One main message. If the viewer needs more than ~3 seconds to know what the piece is about, cut copy or enlarge the hook. 3-second test is a **working default** from poster practice (Baumann; Cedilla walk-past test).

## 2. Headline length and role

- Headlines are short hooks, not paragraphs. One thought; explanation goes in the subhead. Source: Felici / CreativePro.
- Suppress hyphenation in headlines; keep lines together. Source: Butterick, *Headings*.
- Prefer bold over italic for display emphasis. Source: Butterick.
- All caps: fine for **less than one line**; never multi-line body. Add **5–12%** letterspacing to all-caps / small-caps. Source: Butterick, *Letterspacing*.

## 3. Type pairing (max 2 families)

- Default: **one family** with weight/size contrast. A second family only when the first can't do the job. Source: Google Fonts Knowledge (*Pairing typefaces*); Butterick (*Mixing fonts*).
- Poster/social: **display + plain text**, max two. Source: Cedilla and social design guides (corroboration only).
- Contrast by weight and width (ExtraBold vs Regular; condensed display vs normal body), not by stacking lookalike sans faces.

## 4. Tracking, leading, kerning

| Setting | Guidance | Source / status |
|---|---|---|
| Large display tracking | Tighten so spacing looks normal, not slack; white space grows faster than glyphs as size rises | Felici/CreativePro; Fonts.com / Strizver |
| Reverse (light on dark) | May need slightly **more** tracking than dark-on-light | Fonts.com |
| All-caps / small-caps | **+5–12%** letterspacing | Butterick |
| Body leading | **120–145%** of size | Butterick |
| Display leading | Tighter than body; set optically so lines don't stripe | Felici; **working default** ~0.9–1.1 for short display stacks |
| Mobile caption leading | ~1.3–1.5 when more air is needed | working default |
| Kerning | Always on; hand-kern large headlines; start from the loosest pair (LA, WY) | Butterick; Felici |
| Connecting scripts | Do not track; breaks joins | Fonts.com |

## 5. Line length, rag, widows

- Body measure: **45–90 characters**. Source: Butterick, *Line length*. Poster body can be shorter (Baumann: ~10–12 words).
- Prefer flush left / ragged right for marketing blocks; centre sparingly. Source: Butterick.
- Fix ugly rags by editing breaks, not by justifying short display lines.
- Avoid a single short word alone on the last line, and lonely subheads. Source: Butterick (*Widow and orphan control*).

## 6. Alignment, grid, negative space

- Work outward from the text; don't fill the frame. Source: Butterick ("Don't fear white space").
- Relate every element to existing ones; use a grid and shared edges. Source: Butterick; Müller-Brockmann grid tradition.
- One primary object + one primary type block. Keep margins honest; don't push type into chrome.

## 7. Contrast and text on photos

- WCAG 2.1 AA: **≥4.5:1** normal text; **≥3:1** large text (≥18pt / ≥14pt bold). AAA: 7:1 / 4.5:1. Measure against the pixels **behind each letter**, not an average. Sources: W3C WCAG 1.4.3; technique F83.
- Fixes: darken/blur photo under type, semi-opaque scrim, floor-fade gradient, solid panel, or (last resort) text halo. Source: NN/g *Text Over Images*.
- Never place copy across faces, hands, or the focal subject; prefer the opposite side of the subject (**working default**).
- White text on busy midtones fails often — check the worst patch with a contrast checker.

## 8. Mobile / feed / Story checks

- Zoom out to feed/thumbnail size and confirm the hook still reads.
- Keep critical type inside platform safe zones (Story UI eats top and bottom). Brand Story numbers win when set.
- Thin weights and hairline serifs break when compressed — prefer sturdy strokes for feed (practice guidance, corroboration only).

## 9. Offers and numerals

- Make the number the hero. Keep the % optically balanced — often slightly smaller or baseline-shifted vs the digits (**working default**).
- Lock offer strings from brand copy; never rewrap mid-number or clip the numeral.
- Use lining figures for offers and CTAs when the font has them.

## 10. Spanish (es) specifics

- Glyphs required at every weight used: **á é í ó ú ü ñ ¿ ¡** plus uppercase accents. Test a full string at display size before committing a face. Sources: Briggs; WebPeak; TypeTogether.
- Always use inverted **¿ ¡**. Source: Briggs; TypeTogether.
- Headlines in **sentence case**, not English title case; months, days and nationalities lowercase. Source: WebPeak.
- Accents and ñ need clearance — don't crush display leading. Sources: Briggs; WebPeak; Material language-height note.
- Length: Spanish often runs about **20–25%** longer than English (Language Solutions; Briggs ~140%; WebPeak 15–30%). Design to the Spanish string; don't shrink type to fit an English box.
- Hyphenation: use a Spanish dictionary; prefer none on short headlines; avoid justified short posters. Source: TypeTogether; Butterick.

## 11. Legal / disclaimer type

- Legal stays legible: high contrast, full width when required, never over busy photo without a bar.
- Follow jurisdiction and brand minima (height % of frame, weight, permanence). Legal is never decoration.
- Use the brand body/legal face (readable grotesque), not the display face.

## Applying to Warwin

Map these rules onto existing Warwin constants (see `warwin-brand-guide` and `warwin-compliance-check`). **Do not change brand tokens to match research.** Flag conflicts.

| Topic | Warwin constant | Notes |
|---|---|---|
| Display face | Manrope ExtraBold | Sturdy display; confirm accents at ExtraBold |
| Body / legal | Inter | Matches the plain second-face guidance |
| Alts | Plus Jakarta Sans (corporate); Archivo (sports posters) | Still max 2 faces in one piece |
| 1080-wide sizes | Headline **70–110px**, subhead **30–42px** | ~2–2.5× step, within the poster working default |
| Colours | Navy `#07122F`, blue `#008DFA`, white, secondary `#B8C2D9` | Prove white/#B8C2D9 over photo patches; navy panels pass easily |
| Margins | 60–80px edges | Keep; don't steal for bigger type |
| Stories | Top **250px** + bottom **340px** clear | Paid Stories may need more bottom clearance — flag per buy |
| Legal | National legend band **≥10%** height for paid/affiliate; +18; CABA line when CABA-targeted; "Aplican TyC" with offer | Compliance wins |
| Offer | Exact: "Hasta 350% en tus primeros 3 depósitos" | Big numerals; never clip "350%" |
| Copy | es-AR voseo; captions verbatim from brief when specified | Accents + ¿¡ mandatory |
| Layout | One main object; character opposite the text block | Matches "don't cross faces" |

### Conflicts to flag (do not auto-fix)

1. Tight display leading (~0.9–1.1) vs es-AR accent clearance — prefer optical leading that clears ÁÉÍÓÚÑ even if looser.
2. Butterick's "don't centre / don't all-caps headings" vs centred marketing lockups — allowed only if under one line, letterspaced 5–12%, and the brand template already centres.
3. Warwin Story bottom 340px vs Meta paid Stories safe-zone guidance that may clear more — confirm per buy type.
4. `#B8C2D9` on navy is fine; over mid-tone photo it often fails WCAG — scrim or switch to white.
5. The ≥10% legal band shrinks the type area — the hierarchy must still fit above it without dropping below brand size floors.

## QA checklist (before export)

- [ ] ≤3 type levels; hierarchy obvious at feed/thumbnail size
- [ ] ≤2 families; roles consistent (display vs body/legal)
- [ ] Headline kerned; large display tracking not slack; all-caps +5–12% if used
- [ ] Leading clears accents; no collisions on ÁÉÍÓÚÑ¿¡
- [ ] Comfortable line lengths; no one-word last lines; no bad rag
- [ ] Type inside margins and channel safe zones; Story chrome clear
- [ ] No type across faces, hands or focal subject
- [ ] Contrast ≥ WCAG AA on the worst background patch (scrim if needed)
- [ ] Offer numerals intact; locked offer string exact; % not clipped
- [ ] Spanish: sentence case, ¿¡ present, glyphs render in every weight used
- [ ] Legal/disclaimer meets brand height/% rules and stays readable
- [ ] 3-second / distance test passes
- [ ] Run the brand compliance check after type QA

## Out of scope

Posting, scheduling, boosting, generating images, or changing brand tokens. This skill only governs how type is set and reviewed.
