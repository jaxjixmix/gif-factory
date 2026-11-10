# A Tea Party Brought by the Wind (风送来的茶会) · Compact Storybook (紧凑动态绘本)

[Back to home](../../../README.md) · [Style guide](../../../styles/compact-storybook/STYLE.md) · [Full Skill](../../../skills/compact-storybook/SKILL.md)

The little bear sets out three cups and asks the girl to fold the invitation into a paper bird. The fox receives the letter and comes to visit bringing a piece of autumn; in the end everyone presses the day into the storybook.

## Real-book and handwriting editions

<table>
<tr>
<td align="center" valign="top"><strong>Landscape · text left, image right</strong><br><a href="realbook-writing.mp4"><img src="realbook-writing-preview.gif" alt="Landscape preview of the real book with body text being written" width="440"></a></td>
<td align="center" valign="top"><strong>Portrait · image top, text bottom</strong><br><a href="portrait-writing.mp4"><img src="portrait-writing-preview.gif" alt="Portrait preview of the white-framed book page with body text being written" width="200"></a></td>
</tr>
</table>

[Watch / download landscape](realbook-writing.mp4) · [Watch / download portrait](portrait-writing.mp4). Both editions are 54 seconds, 12 pages, 6fps, with the same 15 body-text writing sequences and music.

Landscape: 1920×1080, effectively 6fps, 324 frames, 12 pages; a straight top-down shot of a thin-paper book with the original illustration animation. The 15 body-text sequences are written out quickly as each page lands, with a light rustling sound. Title and page numbers are static. The layout and the three-page writing sample have been accepted; the full version has been checked sequence by sequence for text and sound timing.

Portrait uses the **mobile reading optimised edition: 1080×1920, 54 seconds, 324 frames**, with each page image on top and two centred lines of handwriting below. Illustrations are enlarged to 912px and body text to 78px, reducing the side desk margins and leaving room for the right-hand interaction column and the bottom title; the white frame, real paper texture and wooden surface are kept. A separate blank portrait page was made with the landscape base plate as the material reference, and the original animation was re-arranged; the landscape book was not scaled down or cropped. The 15 body-text completion states, page turns and audio track have been checked — see [portrait specification check](portrait-verification.json).

**Music production note**: the soundtrack can be made separately with tools like Suno or Gemini, then exported and handed to this pipeline for mixing. This case uses "Candle at Dusk", produced and supplied by the user through Gemini; the first 54 seconds are used, lowered in volume with fades at both ends. No claim is made that Suno was used for this case, and the underlying model is not guessed. The writing sound effect comes from [SFXMint](https://sfxmint.com/sounds/pencil-writing-01), credited as CC0 and AI-generated. Music, sound effects and code are licensed separately; the music does not automatically carry the repository's MIT rights.

The real-material base plate was made by editing the accepted book image to remove text and illustrations, then compositing the original font and character animation back on. Standard stroke-order centre lines approximate the handwritten glyphs; no claim is made that the font's real writing trajectory was recovered. No system fonts, the original track or the full stroke-order data are bundled.

## 12 standalone page action clips

[Download all standalone actions](pages.zip). Below are the raw single-page assets without the book frame, useful for referencing the motion or continuing your own edit.

| Page | Action | Page | Action |
| --- | --- | --- | --- |
| 01 | [The water's nearly boiling](pages/01.mp4) | 07 | [So it's an invitation](pages/07.mp4) |
| 02 | [Three cups](pages/02.mp4) | 08 | [Bringing a piece of autumn](pages/08.mp4) |
| 03 | [Send this letter for me](pages/03.mp4) | 09 | [Warm light ahead](pages/09.mp4) |
| 04 | [Fold a paper bird](pages/04.mp4) | 10 | [Finally, you're here](pages/10.mp4) |
| 05 | [Follow the wind](pages/05.mp4) | 11 | [Blowing on it together](pages/11.mp4) |
| 06 | [Lands at the nose tip](pages/06.mp4) | 12 | [Keeping today](pages/12.mp4) |

## Method and checks

Character references were used in image generation; transparent key poses are composited frame by frame over a fixed background, the paper bird is joined using trajectory and palm anchor points, and page turns were made separately. No continuously generated video or frame interpolation was used.

The actual export frame rate, duration and frame count were verified, and the first, middle and last frames plus prop hand-offs were checked; the paper bird's landing point and the cups' desk position were corrected. The real-book and writing samples have been accepted, and the 54-second film has passed page-by-page and audio checks. Specification records are in [verification.json](verification.json); a specification check does not mean every new story will automatically be stable.

This directory publishes the current film, the standalone action clips and previews. Reusable production rules and check scripts live in the standalone Skill; no system fonts or private source images are included here, and no exclusive commercial rights to the case assets are promised.
