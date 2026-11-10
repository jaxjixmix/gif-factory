# Lenticular Card (电子光栅卡): first check whether the images can be paired

This is a separate output category: one image switches between two states, A and B, via fine strips, mimicking the transformation effect of a physical lenticular card. Photos, anime, illustration, pixel art or product shots are all usable; choose the art style and transformation method separately. The GIF is an auto-looping demo; it does not read viewing angle, and it is not a physical glasses-free 3D or interactive card.

The current reference is [nine half-face lenticular cards](../examples/lenticular-cards/), not full character actions, photo walls or brand films. The Polaroid direction is paused; do not mix it into this category.

If the user wants the title to change too, a show teaser, or integrated figure-and-lettering design, route to [dynamic posters](dynamic-posters.md). The fixed-title default below belongs to collector cards; it does not override the Type-Linked (文字联动) requirement of dynamic posters.

## What images suit this

| Input | How to handle it |
| --- | --- |
| Two images at the same angle and pose, with similar lighting | Preferred. Real face/face-mask, daily/transformed, open eyes/blinking, and two product colorways are all worth trying |
| One pre-aligned left/right face-split image | Separate the two sides; mirror when needed, then check eyes, nose tip, mouth and chin. Mirroring cannot fix different camera angles; state that the final result only shows the half faces the source already has |
| One complete figure image | Design the other state first, then generate or find a matching image; a single image does not contain the other state, so do not promise a direct transformation into another character |
| Full-body character art/product images | Try a two-state card first, keeping silhouette, position and light direction; do not auto-crop to a half face — half-face is just the current series' choice |
| Landscapes, group photos, images with very different actions | Try only with an explicit two-state design and a valid static pairing; do not default them into the face-switch pipeline |

Judge images by the pairing conditions, not by character name. Popular IP may be blocked by the generation service, and one attempt may succeed while another fails. Technical fit, generation success and source rights are three separate things; do not write a few results up as a character allowlist or blocklist.

## Checks before starting

- **Matching composition:** same side profile and similar pitch and turn angles. Between a front face and a marked profile, chin, nose bridge and ears still jump position even if the eyes are moved together.
- **Anchors line up:** compare eye position/eye line, nose tip, mouth, chin, outer contour and shoulder line across the A and B stills. Uniform scaling, translation and slight rotation are fine; do not separately widen the face, squash the head or distort the features.
- **Enough canvas:** this series defaults to 480×720. If the reference specifies a size, keep that size; to show the chin, the source must have a chin, or regenerate/repaint first and re-check. Changing the canvas to 320×720, or shrinking the face and padding with big black bars, does not fulfill the 480×720 composition requirement.
- **Enough clarity:** judge the original face crop at the final size. Keep the effective crop no smaller than its display size where possible, and allow higher resolution for detail-heavy material. A low-quality image can be tried as one card first, but upscaling and the word "HD" cannot restore skin, eye or material detail that does not exist.
- **Both states complete:** no missing eye, mouth, chin or target prop; no leftover fragments of the other side's mask on the face. If only a broken half remains, change the source or redo the state image.
- **Backgrounds that join up:** a complete figure silhouette against natural shadows on a unified dark background is usually more stable than stitching a city. When outpainting or recompositing, keep the person's true proportions and review the still first; do not pass off obvious collage strips, repeated buildings, mirrored backgrounds or stretched blur bands as natural extension. Distinguish the source's own dark areas from a black bar patched in by hand.
- **Consistent material:** unify art style, lighting, sharpness and color tone where possible. Photos and drawings can be mixed by user choice with the difference stated; do not describe illustration as live-action footage. Preserve sources and the actual generation modes, and separately check the rights needed for commercial use.

When anchors conflict badly, the silhouette is missing, outpainting fails or detail is insufficient, provide substitute material/a matching still first. Do not keep hiding a mismatched pair behind fast switching, strong flashes or more strips. When the user explicitly keeps a version, keep it by file version; do not silently replace it just because another version crops more completely.

## Material and workflow

1. Carry forward the user's latest chosen dimensions, composition and version. For a new composition or source, compare the A and B stills first; an existing qualified pair can proceed directly.
2. For new generations, request both states in the same pose in one diptych, or confirm A first and then edit B with A as reference. Specify the actual eye position, chin, contour and lighting; after generating, verify panel count, actual dimensions and alignment — a prompt is not evidence that they were achieved. Record whether a reference image was used.
3. If generation is blocked, state the failure; do not record an empty result as material, and do not cycle through reworded prompts or alternate services to evade the block. Use existing, usable and lawful sources within the user's authorization; when no suitable material exists, state the remaining blockers. Record what was used for ready-made material, generated material and stitching/outpainting separately.
4. Typeset the title once at composition time and keep it fixed. Finish each card first, then build the overview by taking frames from the **final decoded GIF by playback time**; do not stitch by frame number, because held frames may already be merged.

## Motion and export

- Current series reference: the full frame stays fixed with no camera push, no intro or outro; A holds → vertical strips switch to B → B holds → back to A. Switch between the two states at the same position; do not force limb motion onto the figure.
- Defaults: 6 seconds, 20fps temporal sampling, infinite loop; these are current-series defaults and can change by user request. Do not pass off "8 frames total" as 20fps; identical held frames merging into fewer encoded frames is normal — report the actual frame count and **cumulative playback duration**.
- The lenticular strips carry the transformation transition; they are not just an ordinary crossfade. Keep the static endpoints as sharp as possible. A physical-card tilt feel can be added as a small perspective move on request, but the current half-face posters do not move the whole frame by default. Iridescent film is an optional material treatment; it does not mean lenticular transformation has been implemented.
- Use [export_lenticular.py](../scripts/export_lenticular.py) to export two images that are **already aligned and composed**. It does not generate the second state, cut out, add a chin, rebuild backgrounds or auto-align faces; a mismatched aspect ratio is rejected, avoiding silent cropping.

```sh
python3 scripts/export_lenticular.py state-a.png state-b.png out/card.gif \
  --width 480 --height 720 --seconds 6 --fps 20 \
  --footer-height 70 --title "VENOM" --subtitle "EDDIE BROCK / VENOM" \
  --font /path/to/title-font.ttf --subtitle-font /path/to/body-font.ttf
```

For untitled images, the footer, title and font arguments can be omitted. The script requires Python 3 and Pillow. Other compositors must still pass the decode checks below.

<a id="解码检查与交付"></a>

## Decode checks and deliverables

- Confirm size, GIF format, non-zero frame delay, cumulative duration, infinite loop and visible transformation on each file; do not substitute an MP4 or a static cover for the GIF.
- Fixed titles and borders must not flicker with the palette, and the loop must not drop frames at its seam; inspect the static endpoints and the transition's in-between frames. Technical metrics do not replace normal playback and aesthetic review.
- **Shared palette, careful with the transparent index:** the black background must not turn white and faces must not develop black holes. If index 255 is reserved for transparent delta frames, do not crudely map every 255 to index 0; map to the closest valid color in the palette instead. Check the final GIF's black background, faces and captions, not just the RGB intermediate frames.
- This category is opaque, full-bleed-to-edge posters. The older `review_gif.py` checks transparent stickers and safe margins by default; do not use its sticker criteria directly to accept lenticular cards.
- When building an overview of multiple GIFs, sample by each frame's actual duration. Verify that every cell in the overview actually moves; do not repeat one character to pad the count. The ZIP must extract, with its count and files matching the standalone GIFs.
- Deliver standalone GIFs, an optional overview/ZIP, a note of sources and the actual modes used, and any unresolved clarity/alignment limits. Known IP and web material serve as effect demos; the software being open source does not grant commercial rights.

See [the case notes](../examples/lenticular-cards/README.md) for the style and source differences among the nine samples. The user requesting this batch's publication does not guarantee that every character, all photos or any future generation will succeed.
