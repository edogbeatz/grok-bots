---
name: warwin-social-creative
description: >-
  Use when producing a Warwin post, carousel, Story, cover, avatar, Highlight or
  affiliate banner for Instagram, Facebook, X, LinkedIn or affiliates.
---
# Warwin social creative

## Steps
1. **Find the brief item** in `Warwin_Designer_Brief_ES_AR`: S01-S06 (IG, FB, X), L01-L06 (LinkedIn), covers, avatars, Highlights or affiliate banners. Also check the per-piece brief by `warwin-marketer` in `/workspace/warwin/brain/marketing/campaigns/` (`banner-set.md`, `S05.md` and so on): it holds the exact on-image text, text block position, icons, which girl and wardrobe, the legal band and the file name. Copy the text exactly, never generate it in an image.
2. **Decide the channel type:** organic, paid/boosted or affiliate. LinkedIn is always organic only and never shows offers or deposit CTAs. Sexy wardrobe looks (everything except W09) are organic only: never boosted, not for X paid, LinkedIn or affiliates unless Edgar and `warwin-marketer` approve.
3. **Get the visual:**
   - character plates via `warwin-character-generation` (profile A or B, one per image; pose chosen against the text block, a distinct pose per size)
   - game art only from the site or official provider materials
   - football scenes with no real clubs, players, crests or the AFA
   - LinkedIn uses the corporate capsule
   - work one piece at a time unless Edgar says to batch; send 2-4 pose options with layout maps, and wait for his pick before polishing
4. **Assemble in Figma** (`user-Figma--paid`) following `warwin-brand-guide`:
   - start from the template frame for the size
   - one main object
   - the real SVG logo and the v8 5-peak crown composited over the plate
   - copy in Manrope and Inter with 60-80 px margins
   - the `Offer/350` component when relevant ("Hasta 350%" + "en tus primeros 3 depósitos", always together)
   - the correct `Legal/LegendBar` variant: the national legal bar (at least 10% height) for paid and affiliate pieces, the solid band for sexy organic pieces (about 135 px main line + 68 px second line on a 1080×1350 post), and the short "+18 | Jugá con responsabilidad" for other organic pieces. Bonus pieces add "Aplican TyC".
5. **Build adaptations** as separate layouts, never stretched: X horizontal, Stories inside the safe zone, carousel cards that each stand alone. Each size has its own pose.
6. **Write captions** in voseo from the brief. Where something is new, write it using the copy rules: no win promises, no "recuperar pérdidas", correct accents and ¿¡.
7. **Run `warwin-compliance-check`** and send the pieces to `warwin-marketer` for its check. Fix every failure.
8. **Export** with the naming convention, only after Edgar has picked. Affiliate size limits: 150 KB or less, 200 KB for 970×250, 1 MB for vertical. Deliver PNGs plus the Figma link, and keep separate layers for handoff.
