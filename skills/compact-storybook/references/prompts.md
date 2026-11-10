# Generation templates

View the reference images first and record what was actually used. Set reference images, size and transparent-background parameters according to the tool's capabilities; writing “transparent” in the prompt cannot substitute for a real alpha output. Replace the bracketed content below before use.

## Action pose sheet

```text
From the provided character reference, make a key-pose sheet for one single action.
Keep [art style, face shape, hairstyle, costume, palette, material, character proportions].
Fix the [full-body / half-body] view and lighting; equal cells, [columns] columns × [rows] rows, ordered left to right, top to bottom.
Keep character proportions constant and the foot baseline stable; hair, hem, hands and feet stay complete inside their cells.
Action: [specific action]. Start from [previous page's end state], finish at [result that can be held].
Key changes: [individual poses for preparation, contact, weight shift, settling].
Head, body and hands change together; do not move only one hand, and do not exaggerate deformation just to add change.
Props: [count, colour, form, holder; whether included in the pose sheet].
Only the character and specified held items, native transparent background, no grid, text, numbering, environment or extra props.
Do not change clothes, do not change the face, do not draw extra limbs, and do not automatically reset the end state to the start.
```

When one pass is unstable, reduce the cell count and draw on from the confirmed character reference and the previous batch's end state. Fix one page first; do not retry the whole set without limit.

## Static background

```text
Fixed background for the same story: [space, time, lighting, material, art style].
Keep environment, colour and perspective from the provided [previous page / scene image].
Camera: [specific camera position]. Character area: [position], reserving [action space].
Fixed furniture, still life and their positions: [list]. Contact plane: [tabletop / floor area].
Do not draw [characters and moving props composited later]; no text, logos or camera movement.
```

## Same-scene state edit

```text
Edit the provided background, changing only [a single state, e.g. door closed → open / add one leaf on the table].
Keep size, composition, perspective, texture, lighting and the positions of other objects.
Show only [count] [target object(s)]; do not add characters, tableware, furniture or text.
```

After the edit, compare directly against the original image; do not assume consistency just because the prompt says “keep”.

## Catching the paper bird: 18-frame example

Frames 0–3 see the paper bird, turn the head and raise a hand; frames 4–8 approach along an arc with the body leaning slightly forward; frames 9–11 it lands in the palm, aligning with the palm anchor; frames 12–17 settle and hold the caught result, without flying off again. Check anchors against the actual poses; the example frame counts cannot override a user-adjusted tempo.

## Real book and clean base plate

Material draft prompt:

```text
Using the provided layout image as content reference, make a static real-book draft. [Aspect], straight top-down, spine centered, the whole book fully visible, about 86% of the frame width. Thin matte uncoated paper, faint paper grain, natural recessed spine, thin slightly irregular page edges, narrow cloth cover. The book rests naturally on [real wood or fabric]; single window light from [direction]; consistent contact shadows. Keep the accepted text, illustration layout and negative space. No thick brown page blocks, embossed paper texture, plastic rounded corners, specular paper, global sharpening, grungy filter or extra ornaments.
```

Base-plate edit prompt:

```text
Precisely edit the accepted book image: remove all text, page numbers, rules and illustration from both pages, restoring blank matte paper consistent with its surroundings. Keep the camera, book boundaries, position, size, spine, cloth cover, thin page edges, wood grain, lighting and shadows. Do not move or redesign the book, leave no lettering or character ghosts, and add no objects. The original animation and final text are composited back afterwards.
```

A generated draft only confirms the outer material quality; the final characters and body text are rebuilt from the original assets, not from the draft's redrawn glyphs and character details.

## Landscape material to portrait single-page base plate

```text
Using the accepted blank landscape book image only as reference for paper, wood surface, cloth cover and lighting, make a 9:16 portrait blank background. Straight top-down, showing only one blank portrait page with a thin page layer below it, no left/right spread or centre gutter. The single page takes most of the frame width with quiet tabletop above and below; all four edges fully visible, faint paper grain, matte thin paper, narrow cloth cover and natural contact shadows. Keep the reference's material style without carrying over the landscape two-page composition. Do not draw text, page numbers, illustration, decoration or ornaments. This image is for compositing the original animation and final text later.
```

After generation, re-mark the usable area from the actual paper edges instead of placing the animation from prompt coordinates alone.
