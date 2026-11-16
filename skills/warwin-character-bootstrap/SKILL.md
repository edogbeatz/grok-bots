---
name: warwin-character-bootstrap
description: >-
  Use once to create, or later to re-train, a locked Warwin brand character
  profile (A Reina with black buns, or B the blonde) in Higgsfield: master
  sheet, Soul ID, reference elements and character bible.
---
# Warwin character bootstrap

Background: `/workspace/warwin/research/skills-research.md` sections 2.3, 2.4 and 4, and the bible `/workspace/warwin/character/warwin-character-bible-v1.md` (§24 two profiles). Warwin owns the rights to the original face (confirmed by Edgar on 2 Nov 2026). Work in `/workspace/warwin/character/`.

Warwin now has TWO brand girls (Edgar, 3 Nov 2026). Run this recipe once per profile and never mix their refs:
- **A, "Reina"**: dark. Locked master face beebeaf8, JET-BLACK messy double buns, grey-green eyes, freckles, 5-peak crown. Already bootstrapped through master and casual face; Soul ID and a clean pure-A reference element are still TODO (element `01311b90` is a hybrid, don't use it).
- **B**: blonde. B1 `1f55b8bb` face (amber eyes, freckles, lip mole) with honey buns and darker roots (H6 `5a993f09`). Formal master lock, name, Soul ID and reference element are still TODO.

## Steps
1. **Source.** Get the profile's approved master image(s) at full resolution (A: `master/LOCKED/`; B: B1 plus H6). Save under `source/` or `master/LOCKED/`. Never base a profile on a real person or celebrity, and photos of real people are text-only inspiration.
2. **Bible.** Keep `warwin-character-bible-v1.md` current: identity (working name, 27-32 look, jaw and cheekbones, eyes, brows, nose, lips, one consistent mark), hair spec, crown geometry with the #0085EB glow, realistic body proportions, wardrobe capsules (see the wardrobe library and `warwin-character-generation`), expressions, lighting and grade, forbidden list, change log.
3. **Quote first.** Every Higgsfield generate or train call gets `get_cost:true` or `prepare` first. Tell Edgar the total and get his OK before spending more than the agreed budget.
4. **Master sheet.** Run Higgsfield's `character-sheet` workflow (from `get_workflow_instructions`) on `nano_banana_pro` or `seedream_v5_pro` with the master as reference: front, three-quarter left and right, profile, waist-up and full body, plus 6 expressions, on a neutral background. Include the SKIN REALISM block from `warwin-character-generation`: visible pores, slight redness, matte, no airbrushing.
5. **Curate 12-20 training images** per profile. Vary angle, light and 2-3 outfits; crown on and off; face clearly visible. No sunglasses, no heavy filters. Only approved, skin-real images.
6. **Train the Soul ID** per profile (for example "Warwin_Reina_v1" and a B name) via `show_characters` (action train). Wait until it's completed.
7. **Reference elements.** Create a pure face element per profile plus `warwin_crown` (prop) with `manage_reference_elements`. Use only completed elements.
8. **Record IDs.** Put the soul_id, element ids, master seed and model versions in the bible and `ids.json`, and ingest into the brain (`character/profiles.md`, `log.md`, run `tools/lint.py`).
9. **Test.** Make 4 images across `soul_2`, `nano_banana_pro` and `seedream`. QA each against that profile's master. Show Edgar the master sheet and test set for approval before declaring the profile locked.
10. Upload the approved master sheets and cutouts to the Figma Character page (`user-Figma--paid`).
