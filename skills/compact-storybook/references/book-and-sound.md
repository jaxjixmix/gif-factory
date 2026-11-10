# Book and sound: verified deliverable method

## Decide the material first, then build the animation shell

A flat rectangle with paper texture, warmed up in tone, is not a real book. Make a static material draft first: pages with a natural slight curl, a recessed spine, thin and not perfectly even page edges, and contact shadow between cover and table. Choose a clear but quiet wood or fabric background; do not pass off busy wood grain, noise and a yellow filter as material quality.

Accepted final direction for Tea Party Brought by the Wind: straight top-down, matte thin paper, faint paper fibre, light wood tabletop, narrow cloth cover, the book about 86% of the landscape width. This is the case's starting point; override it when the user specifies other materials. Embossed paper texture, thick brown page blocks, rubber-rounded corners, continuous specular highlights and uniform sharpness across the frame tend to read as plastic. Fix the camera angle, light source and material response first; do not cover them with added noise.

When using a reference image, view it and pass it to the image-editing tool. Keep the user-accepted angle, composition, cover, page edges, wood grain and light direction, and remove all text and illustration from both pages to form a clean base plate. After checking there is no leftover lettering or character ghosting, restore the original animation and final layout; keep provenance and reference links between the base plate and the generated draft.

## Keep in-page animation separate from page turns

- Desk, cover and paper stack stay fixed; the leaf turns around the real spine; never let the tabletop or the whole frame turn with the page.
- The leaf may be cut from the corresponding blank page in the base plate. Source crops and screen coordinates of static pages must correspond one-to-one; no rectangular seams, repeated spines or moving wood grain.
- Blend the illustration into the paper with transparent edges or a suitable composite mode. multiply can keep the paper colour and fine grain but darkens the image; actually check blacks, faces, costumes and white props, and do not apply it to every illustration by default.
- A triangular mesh/strip can produce a short page turn, but it is not a physical paper simulation. Check the before, middle and after frames; 0.5s at 6fps is only 3 frames. When the user wants it finer, adjust the leaf curvature and shadow first; do not silently interpolate to 30fps.
- A page turn freezes the old page at its last state, and the new page underneath starts from its first state; the action runs only inside the page and must not play in reverse during the turn.

## Fonts and layout

The accepted case uses restrained dark-green handwriting; landscape has text left, image right, and portrait has image above, text below with the white border fully visible. Body text comes first; headers and page numbers recede. Break each page into lines from the actual copy, splitting into several reading beats when needed; do not compress letter width, clip glyphs or shorten the duration with fast text swaps.

The font subset must cover the complete story, punctuation, page numbers and end card, not just the 18-second sample. A replacement font needs glyph, missing-character and real phone-size legibility checks; a font used for rendering does not equal a licence to distribute it.

## Extending landscape to portrait

Exported and checked portrait edition of Tea Party Brought by the Wind: 1080×1920, 54s, 6fps, 324 frames, 12 pages, 15 body-text groups. Image above, text below, two lines centered, titles and page numbers static; writing cues match the landscape version, reusing the original music and writing-sound stems directly rather than re-cutting audio and causing drift.

- Use the accepted landscape base plate as the material reference and generate a separate, completely blank portrait single page and background; do not squeeze the two-page spread into the phone frame. The paper has no centre gutter, with a narrow cover, thin page edges and natural tabletop contact.
- After generation, actually view the paper edges before setting the illustration, body-text and page-turn ranges; do not assume the generator followed coordinates exactly. The accepted mobile-optimized page is about x30/y167/1021×1284, illustration x48/y242/912×912, body text 78px, centre x504, baselines 1216 and 1306; these reproduce that base plate only, do not force them onto new art.
- Centre each line by actual glyph width; when characters are written one by one, still set the start from the line's final width so the text does not drift left and right as it fills in.
- Turn only the paper area; do not bring the tabletop into the turn. Cut the page back from the blank paper grain of the same base plate, and check that the generated cover, shadows and tabletop were not mistakenly cut into the back.
- Preserve the full illustration proportion and action space; do not crop heads, feet or held props for portrait. At phone size, check the surrounding white border, text lines and platform occlusion zones; then view the frames of the actual export after all 15 body-text groups finish writing, confirming no clipped glyphs, leftover strokes or edge drift.

## Mobile-reading optimization

On mobile, do not stop at checking the 9:16 size. Make characters and body text clear on a full phone screen first, then arrange the surrounding tabletop negative space; keep the white border, but do not shrink the story to show the whole sheet. The accepted case widens the page about 12% over the first edition, illustration 840→912px, body text 68→78px, titles and page numbers moved up; the same writing duration, actions, music and sound are unchanged.

- The body-text centre axis may shift slightly left to leave room for the right-hand interaction rail; the last line must not press into the account, title or caption area below. The verified composition places key text in a vertical band of about 168–1330px, with about 120px on the right as a conservative reservation guide; this is a layout review range, not a fixed rule or guarantee for any platform.
- Judge occlusion by the target platform's current real interface. Without a device screenshot, a semi-transparent overlay may simulate top, right and bottom occupancy, labelled “illustrative”; do not pass it off as a real platform screenshot or claim every phone has been verified.
- When adjusting the base plate's framing and page size, keep the photo full-bleed to the whole canvas and check there is no transparent or solid-colour strip at the bottom; update the page crop range together with the new base-plate coordinates so the wood surface does not enter the page back.
- A larger font size needs the per-character offscreen canvas, ink scan size, mask and baselines enlarged in step, so glyph tops and bottoms are not clipped. Each line still centres from its completed width, preserving the fast-writing effect.
- Compare before and after at the same timestamp, checking a 360px-wide preview and the completed state of all 15 body-text groups in the actual export. Enlarging only the outside frame without enlarging the body text or key characters is not reading optimization.

## Music

Music may be **made separately by the user in AI music tools such as Suno or Gemini**, exported once satisfied, then handed to this workflow for cutting and mixing. Music the user already has may also be imported; no particular platform is required, and do not describe this Skill as bundling music generation or as wired into these tools' interfaces.

Tea Party Brought by the Wind uses the “Candle at Dusk” audio made by the user on the Gemini side and supplied by them. This case does not claim Suno was used; Suno is an example of an optional production tool. When publishing a case, record the user-supplied source truthfully and do not guess an unknown underlying model.

Direction to give a music tool: from the story video, make an easy, warm, intimate lullaby — sparse instrumentation, simple melody, soft midrange, no vocals; no solemn or grand scoring; sound that flows naturally and finishes at the actual runtime. Sound effects and narration are decided separately. Keep the music's source note when publishing; the exact scope of use follows the audio's own licence, and generated music is not automatically MIT like the repository code.

Narration, music and sound effects are decided separately. Do not add narration unless the user requests it; in this case narration is explicitly deferred. The accepted direction is a warm, easy, intimate lullaby, no vocals, sparse instrumentation, continuous sound that does not stutter with the low frame rate.

When the user supplies music, measure duration and level first, then choose the segment that suits the story. Do not infer how it sounds from the title alone; do not claim to have auditioned what you have not heard. The accepted case uses the track's opening, lowered 5dB, 0.6s fade-in and a 2s fade-out at the end; this is a choice for that source, not a universal loudness standard.

When expanding a short sample into a full piece, re-cut from the complete original track and move the fade-out to the new ending; do not loop the already-faded 18-second audio or let the middle fall abruptly quiet. Verify the actual file has an audio track, matching duration and no clipping; the user still accepts the result by ear.

## Expansion and delivery

Expanding an accepted sample keeps the camera angle, characters, font, material and sound choices. A complex gift page may run 7s and the ending 6s; ordinary pages may run about 3–4s, without padding to a target duration. Check every page and page turn; a passed sample does not replace checking the complete story.

Separate delivery status: user-accepted samples, a full version exported and checked, and unconfirmed new materials or styles. The Skill and repository directory may sync documentation; publishing or pushing to a remote follows the user's current authorization, and invoking the Skill is not publication authorization.
