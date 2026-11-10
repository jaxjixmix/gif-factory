# Compact Storybook (紧凑动态绘本)

[Back to style index](../README.md) · [See the full case](../../examples/storybooks/tea-party/README.md) · [Standalone skill](../../skills/compact-storybook/SKILL.md)

One illustration carries a single event to completion: delivering a letter, releasing a paper bird, catching a gift, closing a book. After the action there's a short hold, then the page turns. Good for picture-book stories, character vignettes, brand stories and illustrated narratives.

<table>
<tr>
<td align="center" valign="top"><strong>Landscape · text left, image right</strong><br><a href="../../examples/storybooks/tea-party/realbook-writing.mp4"><img src="../../examples/storybooks/tea-party/realbook-writing-preview.gif" alt="Landscape preview of the real book with body text being written" width="440"></a></td>
<td align="center" valign="top"><strong>Portrait · image top, text bottom</strong><br><a href="../../examples/storybooks/tea-party/portrait-writing.mp4"><img src="../../examples/storybooks/tea-party/portrait-writing-preview.gif" alt="Portrait preview of the white-framed book page with body text being written" width="200"></a></td>
</tr>
</table>

Fixed framing by default, effectively 6fps, about 3 seconds per page; output standalone or inside a flip-book frame. The web preview here loops, but the final film plays the action only once. A low frame rate isn't pixelation — the user's chosen art style is kept as-is.

## What Images Fit

- Illustrations with clear character outline, face and clothing, and enough room for motion.
- Images that break into "start → one action → result".
- Backgrounds that separate from the character and props, with contact points like hands and tabletop clearly visible.

For crowded group shots, heavy occlusion, only tiny faces, or shots needing complex continuous camera moves: tidy the composition first, or make a one-page test. Photo-to-illustration needs an explicit user choice; don't default to the photographic beauty-filter route.

## How to Start

> Use $pixel-gif-sticker-pack, choose "Compact Storybook", and turn this story into a fixed-framing mini-animation. First make one sample page: about 3 seconds, 6 frames; the action finishes and stops, no shot sequence.

You can also install the repo's `skills/compact-storybook` folder separately and invoke it as `$compact-storybook`. The full rules, prompts and check scripts are inside. Combining and exporting through HyperFrames also needs the current environment's HyperFrames tools and matching docs; this skill doesn't bundle image generation or rendering services.

## Verified So Far

"The Tea Party Brought by the Wind" currently ships as a 12-page, 54-second real-book version with fast writing, a soft rustle and music; the book and writing samples have user approval. Not every story is fixed at 12 pages, and short actions aren't stretched to fill two minutes. Art style and story can change; for a new combination, review one sample page first.

## It Can Also Be a Real Book Now

Landscape puts the animation into an open book: text left, image right, straight top-down shot, keeping the thin paper, spine and tabletop texture. Portrait uses a white-framed page with image on top and text below, easier to read on a phone. Both versions share the story assets and are laid out separately.

Confirm the static texture of the book and background first, then composite the animation back in; it isn't recoloring a box and sprinkling noise. For music, tools like Suno and Gemini can separately produce a gentle lullaby, added to the video after export; existing music of your own works too. Narration is made separately as needed.

[Stable production rules](../../skills/compact-storybook/SKILL.md) · [Book, layout and music](../../skills/compact-storybook/references/book-and-sound.md)

Body text can be written onto the page quickly once the turn settles, with a soft rustle; it stops once written, leaving reading time. Titles and page numbers stay static. [Writing-effect rules](../../skills/compact-storybook/references/handwriting.md).

[Watch the full 54-second real-book writing version](../../examples/storybooks/tea-party/realbook-writing.mp4). 12 pages at 6fps, with music and 15 body-text writing passes.

[Watch the full 54-second portrait writing version](../../examples/storybooks/tea-party/portrait-writing.mp4). 1080×1920, sharing motion, writing rhythm, music and rustle with the landscape version; re-laid out for phone reading, with body text and illustrations enlarged, space reserved for the right-side and bottom UI, and the white frame kept on all sides.
