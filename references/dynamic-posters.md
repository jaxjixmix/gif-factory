# Dynamic posters: make one complete poster work, then loop it

Use for show teasers, character promos, event key visuals or product state showcases. Route separately from chat stickers, half-face lenticular collector cards and brand films with a narrative arc. A GIF can use lenticular switching, but "lenticular" is a transition method — it does not mean all posters belong to the collector-card category.

## Two design modes

| Mode | What stays, what changes | Use when |
| --- | --- | --- |
| Preserve artwork + Type-Linked (文字联动) | The original illustration/photo keeps its art style; the character state switches, and the title tightens/expands, outline/solid, offset/tilted | An existing good key visual; wanting an outfit change or event teaser |
| Integrated fusion + Type-Linked | Figure, background, texture, lettering, palette and front/back occlusion are all redrawn together | A pronounced design style is needed, or the original art clashes with the specified type language |

The main approved template is the second one: [the nine-character integrated case](../examples/dynamic-posters/p5-integrated/README.md). P5-style Comic Fusion (漫画印刷融合) is one of its design languages, not the fixed art style of every dynamic poster. The first batch — Luffy, Naruto, Gojo, Miku — is user-accepted; the five later additions extend that series, and "requested for inclusion" is not written up as per-image aesthetic acceptance.

## First judge whether the image works

- Prefer images with a clear single-figure silhouette, a readable face and signature accessories, and space left for the title. When the figure fills the frame, hands are missing or hair is cut off, recompose or regenerate first; do not paste big type over the problem.
- With only one still, generate the other state with it as reference; record whether the original served as identity, action or art-style reference. Do not claim the still itself contains motion.
- When the user wants it to look like the real person/original art, prefer the preserve-artwork mode; integrated fusion changes the art style — do not quietly turn a real person into a comic.
- The two states lock identity, face scale, eye line, camera and canvas while allowing expression, gesture, hair-strand and clothing changes. Not every character needs a microphone: performing, punching, charging up, raising a hand, removing glasses and so on are designed per use.
- Pets, products and mascots can use these design principles too, but this series only validates the character posters shown; make one card for a new input first, with no guarantee that any photo works.

## Make the design and the contrast work together

1. **More than an outfit change.** States such as everyday/on-stage and quiet/outburst should differ visibly in expression, action, silhouette or lighting. When the user explicitly wants only an outfit change, follow that request.
2. **Design each character separately.** Fix one dominant color, one black-and-white relationship, one lettering set and one motion direction. Do not just rename the same template.
3. **Type becomes the key visual.** The title can go from tight outline lettering to expanded solid lettering, or change tracking, size and angle; keep the wordforms readable. Important dates, venues and product information stay fixed.
4. **Integrated fusion redraws everything together.** Limited palette, ink lines, flat shading, halftone dots, angled negative space and lettering share one language. Hair/a hat may cover part of the title above, and a forearm can interlock with lettering below; the face, eyes, microphone or signature prop must stay clear and the full text still legible.
5. **When it clashes, change the design first.** Red-black-white card lettering pasted on a colorful seascape, one block per letter, soft-rendered figures with hard sticker blocks — these were rejected this round. It is not a ban on any cutout, but on a pasted-on look with no shared palette, stroke or motion direction. The successful version redesigned the whole image.

## Two production routes; state which one was actually used

**Complete-poster key states (this round's case):** use the image tool to generate two complete posters, left and right, in one pass; the left has the figure and lettering tight, the right has the figure's action and expanded lettering. Label the identity/action reference and the design-language reference separately. Verify panel count, actual dimensions, text, occlusion, fingers and eye line, then separate A and B and compose the GIF. The lettering forms are already drawn in the two images; this is a two-key-state switch, and must not be described as per-glyph independent warping, live interaction or continuous singing/battling.

**Separate type layer:** figure assets and text are layered, and tracking, position, size and so on are keyed over time. Better suited to tasks that change copy often, need exact brand information or want per-glyph motion. Keep the figure's original art language; handle the title zone and figure zone with separate dynamic masks. Use this route when the letters actually need editing, instead of claiming that text already painted into a generated image is independently editable.

Integrated-fusion prompt skeleton (replace the braces; name the actual characters in the reference images):

> Reference image 1 provides only {character identity and pose}; reference image 2 provides only {the approved design language}. Draw two complete 3:4 posters, left and right, and compose them into a gapless 3:2 diptych. Design the figure, background, halftone and custom lettering together: {limited palette/ink line/shading/negative space}. Left side {quiet state}, right side {action, expression, hair-strand changes}; same identity, eye line, face scale and camera. Accurate text above {name}, accurate text below {title}; right-side lettering {expansion method}. The title relates in front of/behind hair and arms; eyes, mouth and {signature prop} stay clear. Leave an empty black area at the bottom for fixed information. No single-glyph card lettering, photo backgrounds, unrelated characters, extra text or logos.

When the user asks only for a text prompt, do not add image references; record the actual generation mode. See the case's `prompts.json` for the complete prompts used.

## Keep the GIF feel

- The complete composition appears from the first frame; the same poster holds on A → cuts to B → holds on B → returns to A. No intro, camera push, storyboarded narrative or end card. Brand storytelling goes through brand films instead.
- Current-series defaults: 720×960, 6 seconds, 20fps temporal sampling; the type layer can use about 5 key states for a staccato feel, instead of dropping the whole clip to a few frames. Report the actual encoded frame count and cumulative duration; identical held frames merging is normal — this round's single poster is 26 frames, 6000ms.
- Choose lenticular or a short cut for the transition, following the user-approved rhythm; do not default to hard flicker, camera animation or constant warping of the whole frame. A two-key-state switch is not itself full limb animation.
- Fixed information, page margins and captions must not flicker with the palette; share the palette, keep the transparent delta index carefully, and lock the indices of fixed areas when needed. For detail checks, follow [the lenticular export guide](lenticular.md#解码检查与交付).

## Export and re-check

Use [export_lenticular.py](../scripts/export_lenticular.py) to export the type-set and aligned complete A and B images:

```sh
python3 scripts/export_lenticular.py state-a.png state-b.png out/poster.gif \
  --width 720 --height 960 --seconds 6 --fps 20
```

It only switches between two complete images; it does not generate images or animate per glyph. When the bottom layout already exists, do not pass `--footer-height`: that argument draws another footer and cannot stand in for "locking the existing bottom". For a separate type layer or fixed masks, use the appropriate layered compositor and check the final decoded result.

- Check the figures, text and transition frames in the final GIF; do not inspect only the unencoded RGB endpoints. Black backgrounds, skin, lettering and halftone must not show palette holes.
- Cumulative 6000ms (or the user-specified value), infinite loop, non-zero delay, loop seam; the key states must be distinguishable and fixed information stable.
- Sample the overview from the final GIFs **by actual frame duration**, keeping each poster's full aspect ratio. The nine-grid is nine different GIFs; when adding/replacing characters, state the count and positions — do not copy one character to pad the grid.
- Deliver standalone GIFs, a pack preview, the prompts and the actual reference modes. A static cover and ZIP are optional. Sample event information is marked fictional; character and font rights are not transferred with the code's MIT license.
