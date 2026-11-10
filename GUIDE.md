# GIF Factory · Usage & Production Guide

[Back to home](README.md) · [Style index](styles/README.md) · [Full gallery](GALLERY.md)

## How to use

Needs to be used in a Codex that can generate images and run scripts.

**1. Install first.** Send this line to Codex:

> Install the GIF Factory Skill for me: https://github.com/jaxjixmix/gif-factory

A Skill is a how-to guide for Codex; once installed, it produces by this method.

**2. Send one image and spell out how many, what text, and how they should move.**

> Use $pixel-gif-sticker-pack; make 25 Chinese-language stickers from the character in this image. I want pixel art, light motion, including “收到”, “好耶”, “抱抱” and “晚安”. Every expression and pose must differ; package them when done and give me one animated preview.

**3. When unsure, look at a sample first.** You can say “just make one to show me”. Once satisfied, say “make 25 like this” and the art style and motion method carry over — no need to describe them again.

## First: what it should look like

| Art style | What it feels like | Good for which images |
| --- | --- | --- |
| Pixel | Characters like those in a small game, blocky pixels you can see | Whale Maid (鲸鱼娘), pixel Little Secretary (小秘书), pixel mascots |
| HD illustration | Anime, chibi or illustration look; linework and clothing detail clearer | Anime characters, mascots, photo-to-anime |
| Photographic | Keeps the person's look and real texture from the photo | People photos, realistic pet photos |

Photos can also be converted to pixel or illustration; photographic is not the only option. Just describe clearly the feel you want to keep.

A Clay Mascot (黏土吉祥物) can be made too: its material, volume and lighting are preserved, via HD consecutive-pose compositing. It looks like clay animation, but that does not mean a real 3D model was made. Paper collage is the treatment for scenes; the character does not need to become paper too.

## Next: how it should move

**Light motion: one expression and pose per sticker, then a small, light animation.**

For example a nod, a bounce, a small sway, with a few little hearts drifting by. Good for everyday chat and making a big set at once. Each sticker still gets a different expression and pose — not one image with only the caption swapped.

**Full action: the character performs one action continuously.**

For example: lower the head, lift the skirt hem, curtsy, then stand upright; or wind up, then throw a fist up in cheer. Head, body and hands coordinate, and hair and clothing follow along.

Pixel art can do full actions too — the [four-character pixel actions in the gallery](GALLERY.md#表情包展厅) are the example. Whale Maid and Little Secretary's small bounces and sways still count as “pixel + light motion”.

Art style and movement are chosen separately. **“More HD” and “more complete action” are two different things**: a bigger image does not mean more natural motion. Full actions are more prone to face swaps and distorted fingers; look at one before deciding whether to batch.

## Finally: chat, lenticular cards, dynamic posters, storybooks or brand films

For chat, make one standalone sticker GIF per entry. For collectible cards, dual identities or two product states, make a Lenticular Card (电子光栅卡); it also delivers standalone GIFs, with its own size and rhythm. For brand promo, string the character, product, packaging and actions into a short film: who acts, what they touch, what changes, and finally the brand sticks in the viewer's mind.

What exists so far is the [bakery fusion film](examples/brand-films/manman-bakery/README.md). Coffee shops or independent brands can try the same method; pilot new characters and actions first, and don't treat an unproven effect as a success case.

### Compact Storybook (紧凑动态绘本)

One illustration performs one small action, holds briefly, then the page turns. Defaults: a real 6fps, about 3 seconds per page; characters and props continue from the previous page's result instead of padding time with long stills. The original art style can be kept; no conversion to pixel required.

> Use $pixel-gif-sticker-pack, choose “Compact Storybook”, and first make one page: fixed framing, a single action, just a sample.

[Full example](examples/storybooks/tea-party/README.md) · [Which images suit it](styles/compact-storybook/STYLE.md) · [Standalone Skill](skills/compact-storybook/SKILL.md)

### Dynamic posters come in two kinds

- **Keep the original artwork, animate the type:** for photos or illustrations you're already happy with. The character's state changes together with the type's size, letter spacing and angle.
- **Integrated character, background and type:** when you want a strong comic, print or other design language, redraw the whole image as one. The nine-character set took this route.

Both suit show promos, character marketing and product showcases. Game-character UI is an application scenario too, but a GIF only shows the effect — it is not a clickable interface.

Don't just paste the same display lettering onto different characters. When a change of clothes isn't enough, keep designing expression, pose, hair strands and lighting; face, eyes and key props must stay legible. Production details in [dynamic posters](references/dynamic-posters.md).

## Lenticular cards: what images work

**Best results come from two images that already match.** Same angle, similar pose, eyes and chins lining up — only then does the flip look like the same figure changing state. Photographic, anime, illustration, pixel art and product shots can all be tried.

| What you have | Whether it works, and how to start |
| --- | --- |
| Two face/mask images at the same angle | Best case; first align eyes, nose and chin |
| One left-right split-face image | Take each side separately, mirroring if needed; check each half is complete |
| One complete figure image | Can be tried, but a second state still has to be generated or found; one image cannot guarantee any character flips directly |
| Two colorways of a product, two expressions of a character | Worth trying; object position, outline and lighting should match |
| One frontal face with a clear profile | Swap the pairing first; forcing the eyes together still leaves the nose and chin jumping |
| Chin cut off, face tiny and blurry, outline missing | Switch to a fuller, clearer image first, or redo the stills; stretching the face or adding a black border will not pass as fixed |

This reference is **480×720 half-face close-up**. Want the chin showing? There has to be a complete chin; want to fill the frame? Re-arrange the figure and background first. Faces will not be stretched out of shape to fit the size, the frame never suddenly narrows, and an obviously pasted-in city scene or a blurry color band is not used to fill the right side.

For a new composition, look at the two stills first and animate only when they fit. Whether the figure, art style and angle match affects the result more than the character's name. Popular characters may be blocked by image-generation services; with ready usable material you can switch route, but not every IP can be guaranteed to generate, and one failure does not mean it can never be done.

[Detailed lenticular workflow](references/lenticular.md) · [Nine cases and their sources](examples/lenticular-cards/README.md)

## You can say it directly

For the earlier Whale Maid look:

> Make 25 pixel-art light-motion stickers. Keep the character cute; a different expression and pose on each, with gentle bounces, sways and small icons.

For this batch's four-character pixel actions:

> Make pixel-art full-action stickers, 5 per character. Draw waving, thumbs-up, thanks, thinking and cheering; body, head and hands move together, keep the pixel edges, and the text below stays fixed.

To keep this illustration you have:

> Keep this image's art style and make 25 light-motion stickers. The character nods gently, bounces back, sways; the text below must not wobble along.

To have the character do a full action:

> Make 4 HD-illustration full-action GIFs: waving, finger heart, pumping up and a bow. Head, body and hands must move together; first check for face swaps or distortion.

To try a photographic portrait:

> With this portrait photo, first make one photographic “收到” sticker, light motion. Keep the person's likeness and clothing; do not add beauty filters automatically.

To make a lenticular card:

> Use these two images to make one lenticular card, 480×720, 6-second loop, fixed artwork and title. First check whether the angles, eyes and chins line up. For missing parts, adjust the static images first — don't just crop or patch in a black bar.

For this integrated-fusion look:

> Make a dynamic poster with character, background and type designed together. Limited palette, comic ink lines and halftone dots; the character cuts from calm to burst, the display lettering expanding with it. Hair, arms and title layered front to back; don't cover the eyes or the signature prop. 6-second loop, fixed date and venue, keep the GIF's staccato feel.

To make a brand film with a mascot:

> Use this approved mascot set to make a 15-second brand film. The character acts to trigger the paper mechanism, and the product ends up inside packaging printed with the shop name. Give me the finished film and the editable project.

You can also just say “a set for use at work” or “use my own captions”. Confirmed requests carry forward; if a key point is unclear, Codex will ask you.

## How to reduce choppiness

“Choppiness” here means motion that looks like it is missing in-between frames — jumping forward step by step, or suddenly pausing.

It first checks whether consecutive poses connect naturally, how long each frame holds, and how the end links back to the start. Missing transitions get filled with new poses; if the character's position suddenly jumps, the crop and alignment get checked. It won't just speed up playback and declare the motion smooth. Faces, fingers, clothing and cropping are checked too.

Problems are fixed first, then actual playback is reviewed. A file that opens with enough frames is not automatically called done.

Gallery samples are marked clearly:

- **Accepted**: the user has seen the result and confirmed it as a reference.
- **Pending**: a freshly made test or repaired version, still waiting for the user to view actual playback.
- **Abandoned**: didn't meet the bar, no longer used as a recommended example. One bad output does not mean the character or the whole art style is impossible.

These checks reduce problems; the final call still rests on the actual result. Something tried does not automatically become a “success case”.

## What you get when it's done

- Individual GIFs, each saved and used on its own.
- The whole set as a ZIP, for one-time download.
- An animated preview or preview video, to see the results together.
- Full actions also come with a per-GIF review sheet, for zooming into details.

Pixel defaults to 320 × 320; illustration and photographic default to 512 × 512. Transparent background is the norm; if you have specific size, file-size or background requirements, just say so.

Lenticular cards deliver standalone looping GIFs; in batch, also an animated overview, a ZIP and material sources — no separate video with intro and outro needed.

Dynamic posters deliver standalone looping GIFs plus a compilation preview. The current case flips between two complete poster key states; for word-by-word copy edits, layered type is made separately.

Brand films separately deliver the video, an editable project and necessary asset credits; size and duration follow the use. Making an ad does not automatically regenerate a whole sticker pack.

## The character looks blurry — what now

You can say directly:

> The character looks a bit blurry; first check whether the original image is unclear or the export blurred it. Keep the original detail, then give me a before-and-after at the same size.

Illustration and photographic composite from the original detail by default. Detail the original doesn't have cannot be recovered by simply enlarging. Pixel art keeps its blocky pixel edges — they are not smoothed away to “become clear”.

<details>
<summary>Want to run the scripts yourself? Click here</summary>

Python 3 and Pillow required; preview videos also need FFmpeg with libx264. Prepare the assets and manifest first, and choose a font that supports Chinese.

Manifest and motion options for light motion: [manifest guide](references/manifest.md); production method: [light-motion workflow](references/light-motion.md):

```sh
python3 scripts/export_pack.py manifest.json build --font /path/to/font.ttf --preview
```

For pixel art add `--render-style pixel` to the command. Illustration and photographic use HD compositing by default. Appearance choices: [appearance reference](references/appearance.md).

Full actions for illustration and photographic use [the consecutive-pose workflow](references/keyframes.md) and its own script:

```sh
python3 scripts/export_keyframes.py actions.json build-actions --font /path/to/font.ttf --preview
```

Pixel full actions take the separate [pixel action workflow](references/pixel-actions.md), using the exporter that preserves the blocky edges:

```sh
python3 scripts/export_pixel_actions.py examples/pixel-actions/action-example.json build-pixel-actions --font /path/to/font.ttf
```

The two action scripts each cover their own art style; new characters still get one pilot first, then the batch once confirmed.

[Visual stability checks](references/stability.md) explain per-frame inspection, bad-frame repair and re-checking. [The clarity guide](references/clarity.md) handles blur problems. Review records are tied to the exact GIF version; after an edit they must be re-checked.

Full rules in the [Skill](SKILL.md). Previews are generated from the final GIFs; automated checks cover count, duration, transparent background, cropping and the ZIP — they cannot automatically judge whether the visuals look good.

Brand-film rules: [brand-film workflow](references/brand-film.md); a ready editable example: [the bakery project](examples/brand-films/manman-bakery/project/DELIVERY.md). Sticker export scripts cover character assets; an ad needs a separate editable timeline.

</details>
