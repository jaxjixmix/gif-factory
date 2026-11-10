# Chinese cursive (草书) and three-character signatures

## Typeface and letterforms

- Default to connected and abbreviated strokes grounded in traditional cursive; when semi-cursive (行书) is requested, keep fuller glyphs and fewer hairline joins. Do not merely slant an ordinary font, and do not abbreviate glyphs into arbitrary tangles of line.
- Verify the name character by character, keeping necessary radicals recognizable; confirm the static glyphs first, then animate. The user has chosen the Chinese cursive direction and explicitly accepted the three-character 「卧云间」 (Woyunjian) example; the nine expansions show the design range and do not represent item-by-item approval.
- “Handwritten material feel” uses pressure changes, thick/thin contrast, turns, hairline joins and tapered terminals; a small amount of flying white can serve the stroke momentum, but do not substitute metal, embossing, glow or rough chalk.

## Motif and layout

Chinese designs also need a visible motif beyond the characters. Use abstract lines such as auspicious clouds, moon arcs, star trails and bamboo leaves to echo the glyph shapes; avoid characters alone, or a realistic icon pasted beside the lettering. Keep an actual gap between the upper motif and the lower character body, each with exclusively owned ink.

Two-character names keep a contrast between tight and open spacing. For three characters, rearrange their width, center of gravity and connected strokes as a whole; do not squeeze them into the two-character layout or drop a character. Let the last character's long terminal balance the whole; characters need not be equal width. Keep the 960×640 canvas; scale long names uniformly with margins when necessary, without stretching the glyphs.

When the script is revised, keep the accepted motif, gradient and rhythm; redraw strokes only where the actual geometry requires it. Three characters still use the two visual gesture groups; do not read “three characters” as “three strokes”.

## Motion and Chinese stroke endings

Follow the main flow's 0.30s blank, 0.14s upper stroke, 1.02s pause, 0.18s fast character body and 0.72s terminal deceleration. No underlay, shake, recoil, particles or default audio.

Re-inspect connected components for every image, including tiny flying-white fragments and isolated small strokes. Upper-motif fragments must not be assigned to the character-body stage; Chinese character dots and strokes must not be misattributed to the motif. Do not reuse another image's component IDs.

- For the returning hook of 「月」, trace the actual down-then-return path; a horizontal wipe will not do.
- For the bottom horizontal of 「星」 or the last character's long rightward tail, isolate the complete terminal first, then decelerate along its direction.
- Near a returning loop, exclude the neighboring character body from the terminal region to avoid early appearance or double drawing. The brush may widen over edges; do not hide a wrong assignment behind a wider mask.
- The current raster reveal consists of the two visual gesture groups and a terminal path; it does not automatically recover per-stroke writing order. Do not call it exact stroke-order animation.

First check that the pause shows only the motif, then the character-body-to-terminal handoff, the decelerating ending and the loop reset. When precise per-stroke order is required, build separate stroke layers instead.

## Chinese nine-grid

Finish the nine individual videos first, then compose with make_grid.py. Labels must use a font that contains Chinese glyphs; Noto CJK can be selected automatically, or pass --font explicitly. Do not let a static collage stand in for the motion nine-grid.

[Nine-grid cover](../assets/media/chinese/nine-grid.png) · [GIF](../assets/media/chinese/nine-grid.gif) · [MP4](../assets/media/chinese/nine-grid.mp4)

## Reproducible examples

Run from this module's directory:

```bash
python scripts/render_signature.py inspect --image assets/chinese/Woyunjian.png
python scripts/render_signature.py render --config assets/chinese/Woyunjian.json --out /absolute/output/woyunjian
python scripts/audit_video.py /absolute/output/woyunjian.mp4
```

Config paths are relative to the config file; terminal coordinates are based on 960×640 and must not be copied across designs. All assets are original generated art and finished media from this work; third-party reference screenshots are not included.

| Name | Motif | Gradient | Resources |
| --- | --- | --- | --- |
| 卧云 (Woyun) | auspicious cloud | moon white→light cyan | [source art](../assets/chinese/Woyun.png) · [config](../assets/chinese/Woyun.json) · [GIF](../assets/media/chinese/Woyun.gif) · [MP4](../assets/media/chinese/Woyun.mp4) |
| 栖月 (Qiyue) | moon arc | moon white→pale indigo | [source art](../assets/chinese/Qiyue.png) · [config](../assets/chinese/Qiyue.json) · [GIF](../assets/media/chinese/Qiyue.gif) · [MP4](../assets/media/chinese/Qiyue.mp4) |
| 枕星 (Zhenxing) | starburst | pale gold→light purple | [source art](../assets/chinese/Zhenxing.png) · [config](../assets/chinese/Zhenxing.json) · [GIF](../assets/media/chinese/Zhenxing.gif) · [MP4](../assets/media/chinese/Zhenxing.mp4) |
| 听澜 (Tinglan) | ocean wave | pearl white→cyan blue | [source art](../assets/chinese/Tinglan.png) · [config](../assets/chinese/Tinglan.json) · [GIF](../assets/media/chinese/Tinglan.gif) · [MP4](../assets/media/chinese/Tinglan.mp4) |
| 竹隐 (Zhuyin) | bamboo leaf | tender yellow→emerald green | [source art](../assets/chinese/Zhuyin.png) · [config](../assets/chinese/Zhuyin.json) · [GIF](../assets/media/chinese/Zhuyin.gif) · [MP4](../assets/media/chinese/Zhuyin.mp4) |
| 鹿鸣 (Luming) | antler | ivory white→amber | [source art](../assets/chinese/Luming.png) · [config](../assets/chinese/Luming.json) · [GIF](../assets/media/chinese/Luming.gif) · [MP4](../assets/media/chinese/Luming.mp4) |
| 惊鸿 (Jinghong) | flying feather | pearl white→vermilion | [source art](../assets/chinese/Jinghong.png) · [config](../assets/chinese/Jinghong.json) · [GIF](../assets/media/chinese/Jinghong.gif) · [MP4](../assets/media/chinese/Jinghong.mp4) |
| 流萤 (Liuying) | firefly trail | pale gold→lime | [source art](../assets/chinese/Liuying.png) · [config](../assets/chinese/Liuying.json) · [GIF](../assets/media/chinese/Liuying.gif) · [MP4](../assets/media/chinese/Liuying.mp4) |
| 松风 (Songfeng) | pine branch | moon white→sage green | [source art](../assets/chinese/Songfeng.png) · [config](../assets/chinese/Songfeng.json) · [GIF](../assets/media/chinese/Songfeng.gif) · [MP4](../assets/media/chinese/Songfeng.mp4) |
| 卧云间 (Woyunjian) | long auspicious-cloud arc | moon white→ice cyan | [source art](../assets/chinese/Woyunjian.png) · [config](../assets/chinese/Woyunjian.json) · [GIF](../assets/media/chinese/Woyunjian.gif) · [MP4](../assets/media/chinese/Woyunjian.mp4) |
