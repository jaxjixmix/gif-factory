# Figure, background and type fused as one · Nine-character dynamic posters

Using a P5-style screen-print comic language, the whole poster is designed as one piece: black and warm white as the base, each character keeping one identifying colour, with figure, halftone shadows, angled negative space and custom letterforms forming front-to-back relationships in one frame. Not paper-card lettering pasted onto the original colour art.

<img src="preview.gif" alt="Nine-character fully fused dynamic posters" width="720">

## Nine standalone GIFs

| Character | Title | File |
| --- | --- | --- |
| Kagamine Rin (镜音铃) | TURN IT UP | [View GIF](01-rin.gif) |
| Megurine Luka (流歌) | NIGHT ECHOES | [View GIF](02-luka.gif) |
| Teto | BREAK THE LOOP | [View GIF](03-teto.gif) |
| Makoto Yuki (结城理) | BLUE HOUR | [View GIF](04-yuki.gif) |
| Miku (初音) | LIVE LOUD | [View GIF](05-miku.gif) |
| Naruto (鸣人) | CHARGE UP | [View GIF](06-naruto.gif) |
| Luffy (路飞) | SET SAIL | [View GIF](07-luffy.gif) |
| Gojo (五条悟) | LIMIT LESS | [View GIF](08-gojo.gif) |
| Goku (悟空) | GO BEYOND | [View GIF](09-goku.gif) |

Each is 720×960, a 6-second infinite loop, actually encoded as 26 frames (repeated hold frames merged), time-sampled at 20fps. The nine-grid is a thumbnail preview — open the single cards for full size.

[Static overview cover](cover.jpg) · [Decode check](review.json) · [Actual prompts](prompts.json) · [Production method](../../../references/dynamic-posters.md)

## How it was made

The built-in image tool regenerated the two complete left/right posters; earlier character pose images served as identity and action references, and the accepted Luffy version served as the design-language reference. Makoto Yuki has no portrait reference image — his identity comes from the text description — and the Luffy image only supplies the design language. The left and right key states carry both figure and letterform changes, then a lenticular loop is made with the bottom information fixed.

The lettering is already drawn into the complete key states, so this cannot be called per-letter independent animation, and the finished piece should not be described as a clickable game interface. When exact brand text needs frequent changes, use the separate layered-typography route.

The first batch of fully-fused versions — Luffy, Naruto, Gojo and Miku — has been accepted by the user; Kagamine Rin, Luka, Teto, Makoto Yuki and Goku are later expansions that passed technical checks, with no claim that the user has aesthetically confirmed each one. Makoto Yuki replaces Kagamine Len (镜音连) in the current nine-grid arrangement; the older Kagamine Len version is left in place.

The event date, venue and show information are all fictional concepts, not an official event. Commercial rights to the character IP, referenced design language and fonts cannot be inferred from the software's MIT license. No font files or private source photos are bundled.

Downloading the whole repository gets you these nine cards and the preview; no large ZIP duplicating the same content is kept in the repository.
