---
name: childhood-ai-avatar
description: Generate or edit identity-preserving childhood and child portrait avatar sets from user-supplied photos, including single recreations, four-image sets, nine-image expression sets, nine-style samplers, and 2x2 or 3x3 contact sheets. Use for requests such as 童年照生图、儿童头像、小时候照片复刻、四宫格、九宫格、多表情、白底悬浮头像、同款风格复刻, or turning a childhood photo into cute studio, plush, clay, anime, watercolor, retro-photo, sticker, blind-box, or papercraft variants. Prioritize the user's identity photo over any style reference and keep every depiction age-appropriate.
---

# Childhood AI Avatar

Create coherent portrait sets whose face comes from the user's identity reference and whose visual treatment may come from a separate style reference. Use the available image-generation or image-editing tool for raster output.

## Operating contract

- Require at least one usable identity photo when the user expects a recognizable person. If it is missing or inaccessible, ask the user to attach it again.
- Treat user photos labeled as the person, original, childhood photo, or “my photo” as **identity references**.
- Treat screenshots, examples, social posts, and “make it like this” images as **style references** unless the user explicitly says they depict the same person.
- Never borrow the face or identity from a style reference. Use it only for composition, lighting, palette, material, and finish.
- Preserve visible identity cues without inventing biographical or sensitive attributes.
- Keep children fully clothed and the styling, pose, props, and framing age-appropriate.
- Describe similarity honestly. Do not promise pixel-identical reconstruction from blurred, obstructed, or low-resolution input.

## Choose the output mode

Infer the mode from the request and proceed without clarification when the intent is clear:

1. **Single recreation** — reproduce one requested effect or portrait.
2. **Expression set** — keep one style and vary expression or small props. Default to this mode for “给我四张/九张” when one example style is supplied.
3. **Style sampler** — keep identity and composition stable while varying the visual style. Use for “多种风格”, “九种效果”, or an explicit comparison request.
4. **Contact sheet** — arrange already-generated portraits into a 2x2 or 3x3 grid. Do not regenerate faces merely to make the grid.

For a nine-image request, deliver nine separate images first. Also deliver a 3x3 contact sheet when the user asks for 九宫格, 合集, 拼在一起, or an equivalent layout.

## Build the generation plan

1. Inspect every available image before generating. When local paths exist, use the image-inspection tool rather than relying on filenames.
2. Label each image internally as identity, style, or both. If the role is genuinely ambiguous and would change the result, ask one concise question.
3. Record only visible, non-sensitive identity invariants: face shape, relative feature placement, hairstyle silhouette, apparent age range in the source, and distinctive benign details.
4. Separate invariants from allowed variants:
   - Keep facial identity, apparent age, hairstyle family, framing scale, background family, and rendering quality stable.
   - Vary expression, gaze, one small prop, or the selected style recipe.
5. For expression sets, read [references/set-recipes.md](references/set-recipes.md). For style samplers, also read [references/style-recipes.md](references/style-recipes.md).

## Construct prompts

Use a stable master prompt and change only the variant block. Keep these blocks in this order:

1. **Task** — state that this is an identity-preserving portrait derived from the identity reference.
2. **Identity hierarchy** — explicitly say that identity comes only from the identity reference and that style references must not alter the face.
3. **Visual treatment** — describe medium, lighting, background, crop, and finish.
4. **Set invariants** — lock apparent age, hairstyle family, clothing family, camera angle, crop, palette, and background.
5. **Variant** — specify exactly one expression/style/prop change.
6. **Quality controls** — request clean anatomy, coherent eyes and teeth, complete edges, and no text or watermark.
7. **Exclusions** — forbid identity drift, adultification, duplicated faces, merged features, extra facial parts, and style-reference identity leakage.

Prefer concrete visual language over vague quality words. Do not identify a person by name unless the user supplied that name and it is needed for organization.

## Generate a coherent set

1. Include the original identity reference in **every** generation or edit call. Never rely on conversational memory alone for facial identity.
2. Include only the minimum style references needed. Follow the active image tool's rules for local paths versus recent-conversation images.
3. Generate one portrait per call. Avoid asking the model to draw nine faces in a single image; that increases identity drift and layout defects.
4. Use the strongest first result as a visual style anchor for later images only when the tool supports multiple references. Continue to include the original identity photo so drift does not compound.
5. Keep the master prompt unchanged across the set. Replace only the named variant block.
6. Regenerate only failed members, preserving successful images and their variant labels.

## Quality gate

Inspect each output and the full set before reporting completion. Score each image out of 5:

- **Identity fidelity (0–2):** facial structure and age read as the same subject; score 0 for identity leakage from a style reference.
- **Set consistency (0–1):** crop, background, lighting, and finish match the intended set.
- **Variant clarity (0–1):** the requested expression, prop, or style is distinct without changing identity.
- **Technical quality (0–1):** no malformed eyes, teeth, ears, hair edges, accessories, duplicated features, text, or watermark.

Regenerate any image scoring below 4, and always regenerate an identity-fidelity score of 0. Compare the weakest image against the best identity match, not only against its own prompt.

## Assemble and deliver

- Build a contact sheet from the accepted individual images using a non-generative layout operation when available.
- Use equal square cells, consistent crop, even gutters, and no labels unless requested.
- Preserve the individual files at full resolution; the grid is an additional deliverable, not a replacement.
- Name files predictably: `01-natural-smile`, `02-big-smile`, and so on, plus `contact-sheet-3x3`.
- State which images were used as identity and style references, what mode was chosen, and whether low source quality limited resemblance.
