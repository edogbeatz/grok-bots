---
name: warwin-brand-guide
description: >-
  Use for any Warwin design task, or a question about Warwin's palette, fonts,
  logo, layout, formats, brand girls or file naming, before opening Figma or
  generating anything.
---
# Warwin brand guide

Sources of truth: the Google Doc `Warwin_Designer_Brief_ES_AR` (Drive id 1gHauCSVfMntmm72yjFo9Oe2AXb9ahYVAQrhI3jkcMO8, read via the `user-Google-drive--goog` connector), the second brain `/workspace/warwin/brain/` (start at `index.md`; `brand/` pages and `marketing/campaigns/banner-set.md` carry the latest per-size briefs) and `/workspace/warwin/research/skills-research.md` (sections 1 and 6). The brain wins if it is newer than this skill.

## Constants
- Market and language: Argentina, Rioplatense Spanish with voseo (Conocé, Descubrí, Registrate, Jugá). Never translate game names or "Warwin".
- Colors: background navy `#07122F`, **official Warwin blue `#008DFA`** (Edgar decided 5 Nov 2026; use for CTAs, UI and graphic accents; Figma token `blue/500` → `accent/cta`, hover `#33A4FB`, pressed `#0071C8`, both derived), white `#FFFFFF`, secondary text about `#B8C2D9`, Argentine sky-blue `#75AADB` and black leather as accents, soft blue glow. The logo artwork keeps its own colours (`#0085EB` crown in the mark, crown gradient `#1C76FF`→`#004AB9` in the wordmark; Figma `logo/*` primitives, logo-only); never recolour the logo.
- Fonts: Manrope ExtraBold for display, Inter for body and legal text (both Google Fonts with á é í ó ú ñ ¿ ¡). Alternatives are Plus Jakarta Sans for corporate pieces and Archivo for sports posters.
- Logo: the original white W with the blue crown. Never redraw it, recolor it or change its proportions. Always place it on a dark background with about 15% clear space. Use the real SVG in `/workspace/warwin/brand/logo/`.
- Layout: one main object per layout, generous negative space (more on LinkedIn), headline 70-110 px and subhead 30-42 px on 1080-wide frames, 60-80 px edge margins.
- Formats: IG 1080×1350 plus Stories 1080×1920 (keep the top 250 px and bottom 340 px clear) · FB 1080×1350, cover 1702×630 · X 1600×900, cover 1500×500 · LinkedIn 1200×1200 (or 1200×627), cover 1512×256 · avatars from a 1080 master (IG 1080, FB 320, X 400, LI 400; legible at 40 px) · affiliate banners 300×250, 300×600, 728×90, 970×250, 320×100, 1080×1920.
- Naming: `warwin_<channel>_<nn>_<slug>_es-ar_<WxH>.png`, with `_cN` for carousel cards (for example `warwin_ig_05_welcome_es-ar_1080x1350_c1.png`).

## The brand girls
Two profiles, never mixed in one image (details in `warwin-character-generation`): **A, Reina** (dark, black buns, grey-green eyes) and **B** (blonde, honey buns with darker roots, amber eyes). Both wear a 5-peak chrome-and-cobalt crown with the W plate (composite the real crown in Figma), have real matte skin with visible pores, and dress in Argentine-feeling pieces (wide vertical sky-blue and white stripes, no crests or brands) combined with black leather, with blue casino chips as a prop and a casino lounge scene. Edgar dislikes a polished studio look. Each banner size gets its own pose, placed opposite the text block. Sexy wardrobe looks are organic only; the paid Meta look is W09.

## Figma file `Warwin — Brand System` (use the `user-Figma--paid` connector)
The pages, in order:
1. Read me / changelog
2. Foundations: color variables (Dark plus Light-corporate modes), spacing, `legend/height-pct = 10`
3. Type styles (Display, H1, H2, Body, Caption, Button, Legal), tested with "¿Qué partido estás esperando? ¡Jugá! Conocé · depósitos ñ"
4. Logo components (full, mark, mono) and don'ts
5. Character: master sheets for A and B, expressions, wardrobe, do/don't board, cutout components
6. Components: `Legal/LegendBar` (National / CABA / Short-organic / Organic-sexy solid band), `CTA/Button`, `Offer/350` (locked), `Icon/Highlight`, `Tag/+18`, `Glow/W-watermark`
7. Templates: one frame per format with safe-zone overlays
8. Production pages per channel
9. QA checklist

## Steps
1. Load the constants above. Re-read the brief or the brain's per-piece file when the task names a specific post (S01-S06, L01-L06, affiliate banners). Copy and layout for banners come from `warwin-marketer`.
2. If Figma is connected, load the Figma `figma-use` skill (and `figma-generate-library` when building the system), then work in `Warwin — Brand System`. Create it with the structure above if it's missing.
3. Use components (logo, offer, legend bar). Never paste a loose redrawn logo or retype the offer.
4. Start from the correct template frame for the platform and size. In the Figma pass, composite the v8 5-peak crown and the real SVG logo, and clean any garbled felt text.
5. Before export, run the `warwin-compliance-check` skill. Export as sRGB, PNG for text and logos, high-quality JPG for photo composites, with names following the convention.
