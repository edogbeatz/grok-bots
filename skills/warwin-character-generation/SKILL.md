---
name: warwin-character-generation
description: >-
  Use for any new image or video of Warwin's brand girls (profile A Reina or
  profile B blonde): new outfit, pose, dealer look, Argentine tee look, banner
  plate or campaign scene, after the character has been bootstrapped.
---
# Warwin character generation

Read `/workspace/warwin/character/warwin-character-bible-v1.md` (especially §21, §24 two profiles, §25 wardrobe) and `ids.json` first. The second brain at `/workspace/warwin/brain/` (start at `index.md`, then `character/profiles.md`, `character/wardrobe.md`, `character/generation-rules.md`) is the live source; if it disagrees with this skill, the brain wins. If the character files don't exist, run `warwin-character-bootstrap`.

## TWO PROFILES (Edgar, 3 Nov 2026, bible §24)
Warwin has two separate brand girls. Pick ONE profile per image and never mix their refs.

### Profile A: "Reina" (dark), LOCKED
- Face: Higgsfield job `beebeaf8-5236-4e9c-a28d-928963751e13`, file `/workspace/warwin/character/master/LOCKED/warwin_reina_MASTER-FACE_full-res_beebeaf8.png`. Casual face: `master/LOCKED/warwin_reina_CASUAL-FACE_edgar-approved_2026-11-02.png` (media `2898f9a9-d512-4121-922d-ed69f9729765`).
- Traits: oval face, defined cheekbones, soft jaw, straight dark brows, light grey-green eyes, light freckles, straight nose, full natural nude lips, about 28-30, Argentine.
- Hair: JET-BLACK messy double buns high on the head plus long loose black face-framing strands (true black, not brown, not blonde, no blue streaks).
- Refs: beebeaf8 (face + black buns; ignore its crown), 2898f9a9 (casual face).
- Never use reference element `01311b90` for new work: it is a hybrid and pulls blonde hair.

### Profile B: blonde (name TBD)
- Face: B1 = Higgsfield job `1f55b8bb-51ea-4495-8303-c6458a966177` (amber eyes, freckles, a small mole above the lip; the short id is rejected by the API), clearly distinct from A. Edgar picked it on 3 Nov 2026.
- Hair: honey-blonde messy high double buns with DARKER ROOTS and face-framing strands. Working hair pick H6 `5a993f09-8fa6-481f-8474-51ef7e3063b6` (match the W12 try-on `c583c8b2`). Not yet formally locked: Edgar effectively chose this look for the S05 banner on 3 Nov 2026. B1's own flatter caramel hair must not be used.
- Refs: H6 (identity + hair), B1 (face), hair crop `650ae634-f63a-4a4c-a25e-c0082c81793d`.
- Never give B the beebeaf8 image, the casual face, or `01311b90`: they carry A's face.
- v12 plates (`master/v12/`) are an A-face plus blonde-hair hybrid: don't use them as a face ref.

### Shared by both
- NO CROWN (Edgar, 4 Nov 2026): neither girl wears a crown, tiara or headpiece in any look, including D28 and D31-D33 and even when Edgar's sheets show one. Write "NO crown, no tiara, no headpiece, bare buns visible" in every prompt, and never pass crown crops (`a8a3013a`) as refs. The old crown design (cobalt, 5 ball-tipped peaks, W shield) is archived in `master/LOCKED/` in case Edgar brings it back.
- NO TATTOOS, NO PIERCINGS (Edgar, 5 Nov 2026): neither girl gets tattoos or piercings. Edgar tried a shoulder tattoo, a hand tattoo and a septum ring on 4-5 Nov 2026 and rejected all of them. Keep skin clean.
- Never use any other generated output as a face reference. Drift compounds. QA against the profile's master, not the previous image.

## SKIN REALISM RULE (both profiles, every image)
Include this block in every prompt:
"SKIN REALISM (top priority): an unretouched editorial photograph of real skin - clearly visible pores on nose, cheeks, forehead and chin; fine vellus peach-fuzz hair catching the light along the cheek and jaw; slightly uneven skin tone with a little natural redness around the nostrils and on the cheeks; natural variation in freckles and a few small moles; fine under-eye texture and faint natural creases; tiny flyaway hairs. MATTE skin with only a soft natural highlight on the high points; NO airbrushing, NO beauty filter, NO smoothing, NO plastic, waxy, glossy, oily, CGI or HDR look; satin-matte lips with natural lip lines."
Light and camera: soft window or practical light, low contrast, no hard rim or hotspots, 35mm editorial-candid feel, subtle grain. Never an overly polished studio look. Reject any output that looks smoothed or CGI at 100% zoom.

## WARDROBE (library: `/workspace/warwin/character/wardrobe/`, `wardrobe_index.json`, brain `character/wardrobe.md`)
Wardrobe media ids can be passed alongside the face and hair refs for try-ons. Edgar's taste (3 Nov 2026): bikini-style and sexy pieces combined with nice black leather, always with the casino vibe, and simpler rather than busier (no harness or belt straps on tees).
- **W09**: the only ad-safe look (paid Meta boosts).
- **W11b**: the Argentine tee with classic WIDE vertical sky-blue and white stripes (about 3 sky-blue bands across the front), never thin and never horizontal, no crest, no stars, no Adidas or other brands, no generated text (a small embroidered W is fine). Stripe media `4a639945-5b18-4262-803d-21bf74ec83a8`.
- **W12**: leather triangle bikini top with celeste trim, belted leather shorts, long open black trench (media `e46a68ff-5d68-404a-9dbf-547f2f2a5789`). A favourite with W11b.
- **W19**: black lace-up corset, leather choker, leather mini skirt, over-the-knee boots, fluffy black fur jacket.
- **W20**: studded leather halter and pleated micro mini. Moderation blocked it twice; needs more coverage.
- **W21 / W21b / W21c / W21d**: cropped wide-stripe tee with high-waisted leather shorts; with a leather bra under the open jacket; with no jacket; and the simple version with no straps (Edgar's current pick).
- **W22**: knotted split sky-blue and white fan jersey with sky-blue satin shorts.
- **D01-D33**: dealer looks; **AR01+**: Argentine tee looks. See below.
- Everything except W09 is organic, site and affiliate-by-approval only, never boosted. Bikini, corset, see-through and cleavage-forward looks need the solid legend band and `warwin-compliance-check`.
- Moderation: Higgsfield blocks bikini bottoms, thongs and revealing bras. Frame waist-up or hip-up, add an open jacket or trench, use high-waisted leather shorts, and keep any bottom under the legal band.
- Photos of real people that Edgar sends are text-only inspiration: never upload them or copy a likeness, crest, number, player name, brand mark, tattoo or drink.

## DEALER LOOKS (Edgar's pose and outfit sheets, 4 Nov 2026)
- Source: Edgar's illustrated 30-look dealer sheet (D01-D30) plus the extra pose sheet (D31 navy gown with high slit and a chip, D32 off-shoulder crop top and pleated mini with a wink and peace sign, D33 leaning on a poker table holding a chip). The catalogue is in `wardrobe_index.json` and brain `character/wardrobe.md`, and the cell crops are in `/workspace/warwin/campaigns/dealer-looks/test5/cells/`. Look names D02-D30 are the agent's readings of the Russian labels, so confirm them with Edgar.
- Edgar's illustrations are outfit and pose guides only: describe them in text and never use them as likeness refs. Render photoreal with the SKIN block, never in the illustrated style. Likeness comes only from the profile's own refs.
- Make every requested look for BOTH profiles in the same pose (A row and B row on one contact sheet) unless Edgar names one girl. Start with a small test batch, then roll out.
- No crowns on any dealer look (see NO CROWN above). For D28 royal, use a blue velvet or fur cape instead.
- Simple white script W on tops only when it renders clean, otherwise plain. An optional small blue W on the cheek works on playful looks (D32). Chips and cards follow CASINO PROPS below.
- Scene: navy and Warwin-blue casino table, 4:5 at 2k, waist-up framing (three-quarter for full-body poses). Organic IG/FB only until `warwin-compliance-check` passes.
- Bikini, beach, sexy costume and bodysuit looks (D11, D14, D18, D19) will likely hit moderation, so plan more coverage (an open jacket, high-waisted shorts, waist-up framing).
- Batches: `generate_image_batch` takes at most 4 `$file` prompts per call, and `jobs_wait` takes at most 12 jobs. A test batch of 8 looks for both girls costs about 32 credits.

## ARGENTINE T-SHIRT LOOKS (Edgar, 4 Nov 2026)
Argentine tee looks are a core track alongside the dealer looks. Render each one for BOTH girls in the same pose, and use Edgar's dealer poses (chip near the face, peace sign, leaning on the table) as well as the lounge poses.
- Tee rules, always: classic WIDE vertical sky-blue (#75AADB-like celeste) and white stripes, about 3 sky-blue bands across the front, never thin and never horizontal. No crest, no AFA badge, no stars, no numbers, no player names, no Adidas or other brands, and no generated text. A small embroidered or printed white or blue script W is fine. Black collar and cuff trim are OK. Stripe ref media `4a639945-5b18-4262-803d-21bf74ec83a8`.
- Variants (catalogue them as AR01+ in `wardrobe_index.json` and brain `character/wardrobe.md`):
  - AR01 = W21d: cropped tee, high-waisted black leather shorts, one plain belt (Edgar's pick).
  - AR02 = W21 with an open black leather jacket.
  - AR03 = W21b: leather bra under an open tee or jacket.
  - AR04 = W11b knotted at the waist with leather pants or a skirt.
  - AR05 = off-shoulder cropped stripe tee with a pleated black mini and thigh-high socks (the D32 cut).
  - AR06 = stripe tee as a dealer top: a black vest or bow tie over it at the casino table (D04 and D33 cut).
  - AR07 = W22: knotted split sky-blue and white fan jersey with satin shorts.
  - AR08 = oversized stripe tee worn as a dress, belted, with over-the-knee boots.
- Styling: always pair with black leather for the casino vibe. Keep it simple, with no harness straps or busy belts. May-sun embroidery and a gaucho silver-buckle belt are optional accents. Blue chips are the prop.
- Fan and match-day posts: celebrate with the tee, chips and a raised arm. No real stadium, club, team crest, trophy or flag on a pole with a crest, and no drinks.
- Compliance: the full tee is ad-eligible only if the rest of the outfit is covered (W09-level). Cropped, bra and mini variants are organic IG/FB only, with the solid legal band.
- QA: count the stripes (wide, vertical), check there are no logos or numbers, and check the face and hair against the profile master.

## CASINO PROPS: CHIPS AND CARDS (Edgar, 4 Nov 2026)
Whenever chips or cards appear, they must look like real casino props.
- Chips: real clay or ceramic casino chips with edge spots (inserts) around the rim, a raised inner ring and a centre inlay that carries the Warwin script W logo. They come in Warwin blue #0085EB, navy #07122F, white and black. Never plain discs. A small denomination is allowed on the inlay ring (e.g. 5, 25, 100, 500) if it renders cleanly; no other numbers or text. Stacks should be neat, of mixed heights, with consistent sizes and edge spot patterns.
- Cards: real standard playing cards with correct ranks and suits, correct corner indices (rank above suit, at top-left and bottom-right), the correct pip count and layout for number cards, and proper court art for J, Q and K. Use a clean, readable hand such as A-K-10 of spades, a royal flush or a blackjack (A plus K). Card backs are navy with a small W pattern. No garbled indices, extra pips or mixed suits on one card.
- Prompt both explicitly, e.g. "realistic casino chips with white edge spots and a centre inlay printed with the Warwin script W logo" and "standard playing cards, Ace of spades, King of spades and 10 of spades, correct corner indices and pip layout".
- QA at 100% zoom: count the pips, read the indices and check the chip logo. For finals, fix any wrong card faces or chip inlays in Figma: paste clean card faces and the real W SVG on the chip inlays. Prop assets live in `/workspace/warwin/brand/props/` (`card_As.png`, `card_Ks_from_plate.png`, `card_10s.png`, `card_back_W.png`, `chip_top_W_blue.png`, `chip_top_W_navy.png`). Prompting alone gets the chip logos right but usually gets cards wrong (wrong suits, extra cards), so ALWAYS swap in the real card faces with a perspective warp for finals, and turn any extra card into a W card back. No cash, no readable money, no real casino brand on any prop.

## KNOWN FAILURES TO PROMPT AGAINST
- Broken or stretched neck: without a crown, the model raises the head to fill the gap. Prompt "natural anatomy, normal-length neck, relaxed shoulders, head upright over the torso at the same height as the reference, empty space above the buns", and never use a broken plate as a pose reference.
- Blue streaks in A's black hair under blue neon: prompt "pure jet-black hair, no blue dye or streaks, neon rim light only". A faint sheen can remain, so retouch it in Figma for finals.
- B's lip mole can render shiny like a piercing: prompt "a small flat matte brown mole", or retouch it.

## Engine choice
- Placing her in scenes and edits: `nano_banana_pro` (2 credits at 2k; jobs report it as nano_banana_2), with that profile's refs.
- Soul ID is not trained yet (needs 5+ approved images per profile). When trained, `soul_2` for portraits and fast iteration.
- Video: a still as start_image on `kling3_0` (about 7.5 credits for 5 s).
- Utilities: `upscale_image`, `remove_background`, `outpaint_image`.

## Style
Palette lock: every image matches the warwin.casino site palette: deep navy #07122F, Warwin blue #0085EB, white, Argentine sky-blue, black leather. No dominant warm reds, golds or greens (the D16 red dress and D28 gold accents are Edgar's explicit exceptions). Casual nightlife style ref: `master/LOCKED/warwin_reina_STYLE-REF_flagtee-leatherjacket-neonlounge_edgar-liked.png` (wardrobe and scene only). Banners use a navy or blue neon casino lounge with natural, photographic poses and empty space for copy. Edgar likes blue Warwin-logo casino chips as a prop (see CASINO PROPS). Fabric garments must be opaque and lined. Logos on clothes are embroidered or printed into the fabric.

## BANNER POSES
Every banner size or format gets its own pose, never one reused pose. Plan the pose with the text block: the girl sits opposite the text column, the gesturing hand points toward the offer, and her hands and chips stay out of the text. The model lands her hand at 85 to 95% of the width and centres wide shots, so write the layout around the hand. Make a layout map (margins, logo zone, text column, legal band) for each option. Copy, icons and text positions come from the briefs of `warwin-marketer` (`brain/marketing/campaigns/banner-set.md` and one file per piece such as `S05.md`); it also runs the compliance check, so send it the options. Do one piece at a time unless Edgar says otherwise. When Edgar sends his own pose sheets, use those poses.

## Logo on clothes
The generated logo is only a guide. For finals, composite the real SVG (`/workspace/warwin/brand/logo/`) in Figma (`user-Figma--paid`), and clean felt text and garbled numbers. No club crests, alcohol, cash or readable money.

## Steps
1. Pick the profile (or both), wardrobe, pose and aspect ratio. Leave room for copy, and for the legend band on paid, affiliate and sexy organic pieces.
2. Prompt with that profile's face reference first, then its hair ref. Restate its locked traits, NO CROWN, the SKIN REALISM block and the known-failure lines (neck, hair colour).
3. Quote with `get_cost:true` and stay within the budget Edgar set. Wait for Edgar's go-ahead when he says to hold.
4. QA each plate against that profile's MASTER: face match (B clearly not A), hair (A pure black, B honey with darker roots), neck and anatomy, no crown, chips (logo inlay) and cards (correct ranks, suits and pips), clearly 25+, opaque wardrobe, hands, text collisions, palette, copy zones. SKIN GATE: reject smoothed, airbrushed or CGI skin.
5. Re-generate rejects from the master refs. Never chain edits from a drifted image.
6. Save under `/workspace/warwin/character/` or the campaign folder with previews, log date, model, prompt, refs, cost and job id in `log.csv`, and ingest the decision into the brain (log.md, then `tools/lint.py`).
