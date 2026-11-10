---
name: compact-storybook
description: Turn a story or illustration into a low-frame Compact Storybook (紧凑动态绘本) with fixed framing, a once-only action and a short hold; deliver standalone page animations or a page-turning collection. Use for compact storybooks, low-frame healing stories and in-page illustration animation; not for looping chat stickers, montage-shot promos or animating real photographs.
---

# Compact Storybook (紧凑动态绘本)

Stable v1.3. The accepted Tea Party Brought by the Wind sample combines fixed framing, real 6fps, once-only actions, handwritten text, a straight top-down real-material book and gentle music. Style and technique are reused as separate layers; pilot a representative page first for a new character, art style or material, and do not treat one case's appearance as a universal requirement.

## Effect and boundaries

One clear action per page: pick up, hand over, fold, set free, catch, put down, close the book. After the action completes, hold briefly, then move to the next page. Characters and props must change state; do not substitute plot with squashing the whole image, waving an arm or moving the camera.

Preserve the user-specified art style. A low frame rate is a movement tempo, not pixel art or reduced clarity; do not automatically turn real people or illustration into chibi.

Defaults may be overridden by the user:

| Item | Starting value |
| --- | --- |
| In-page framing | Fixed; no cuts, no push-in/pull-out |
| Output frame rate | Real 6fps, no interpolation |
| Page duration | About 3s, usually 2.5–4s |
| Result hold | About 0.5–1s, included in the page duration |
| Page turn | About 0.5s, only after the action ends |
| Output | MP4; make a GIF separately when the user needs one |

Do not force 12 pages or 41.5 seconds. Let the action set the duration; do not pad with extended static waits to reach “two minutes”. When the user explicitly needs a long story, add meaningful plot and pages.

## Deliverable formats

- **Landscape page-turning book:** suits a complete story and reading together; text on the left page, animation on the right, legible straight top-down; prefer retaining real paper leaves, the spine, thin page edges, cloth cover and tabletop contact.
- **Portrait book page:** suits phone publishing; image above, text below, two centered lines of handwriting, white border all round; default to the mobile-reading-optimized layout, enlarging the body text and illustration and reserving space for the right-side and bottom interface; make a separate single-page base plate in the same material style and re-lay it out for portrait; do not shrink the whole landscape book down.
- **Standalone page animation:** do not force a book frame when the user only wants the action.

One story shares action assets and copy; design each layout separately. 1920×1080 landscape and 1080×1920 portrait are starting specs and may be overridden. Keep the accepted font where possible; after switching fonts, check all text, and do not distribute fonts you are not licensed to.

By default the body text is written quickly after the page settles — faint writing sound — hold for reading; titles and page numbers stay static. Explicit requirements such as silence or captions shown immediately take priority. For writing direction and sound sync, read [Body-text writing](references/handwriting.md).

For outer artwork, book material, both layouts and music, read [Book and sound](references/book-and-sound.md). That page separates verified method from adjustable parameters.

Music may be **made separately by the user in Suno, Gemini or similar tools and imported**, or may be music the user already has. This Skill handles segment selection, cutting, fades and mixing; it does not bundle those services, and does not treat narration or writing sound as music.

## Work order

1. Continue existing characters, stories and user-accepted samples. For a new project, break the story into “start state → single action → end state” and pilot one representative page; when the user has already authorized the whole set, continue in batch without asking again.
2. Build a continuity table for characters and props: appearance, relative size, holder, count, position. The next page's start state must continue from the previous page's result. See [Production and review](references/production.md) for details.
3. Make the static background and transparent character key poses, then composite them on a timeline. When editing source art, view the actual image first and call the available image tools per their instructions. Use the [generation templates](references/prompts.md) and record truthfully which references took part in generation.
4. Check one page at the real 6 frames, then expand the remaining pages. When unstable, fix poses and anchors; do not hide it with a lower frame rate, blur or fast cuts.
5. When choosing the page-turning book or white-border deliverable, confirm the static book and background material first, then make a clean base plate with no text or illustration and composite the accepted original animation and text back on; do not treat a deformed character from a generated draft as the final animation. The book frame and the in-page animation are independent; during a page turn, freeze the old page at its end state and start the next page from its first state. When using HyperFrames, read the currently available HyperFrames skill and follow its asset-loading, preview, rendering and review contracts.
6. Inspect the actual exported files, then deliver. Unless the user asks, do not automatically upload to the repository, modify other Skills or publish.

## Deliverable checks

- For every page, view the first, middle and last frames of the actual video; for hand-off actions, also view just before and after contact. No floating or duplicated props, no sudden disappearances, no clipping through occlusion.
- The main action happens once and the end state holds; do not automatically reverse it back to the start. Walking may use the necessary gait cycle but must not become a purposeless loop in place.
- Check image stability, face and costume consistency, hand/foot contact, and text legibility at the actual viewing size.
- The inspection script needs Python 3, ffprobe and ffmpeg. Use `scripts/inspect_clip.py` to check actual size, frame rate, duration and frame count, and to extract review frames: `python3 scripts/inspect_clip.py page.mp4 --fps 6 --duration 3 --frames-dir review/page`. File checks do not replace visual judgment.
- Deliver the whole book, chapters or standalone pages as the user needs them; state actual duration, frame rate, whether there is sound, and anything unfinished. Keep assets, prompts and editable projects as needed; do not write local absolute paths or private source art into a reusable dependency.
