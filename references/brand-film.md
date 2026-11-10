# Brand films: character actions × collage storytelling

Use this workflow when the user wants a character, mascot or sticker pack used for a shop, product or independent brand promo. Carry forward the accepted character appearance and movement method; purpose does not change the character's art style. Clay is a character material treatment, and paper cutout is a scene and narrative technique — neither means every character must be converted to that look.

## Let the character drive the story

For each shot, decide first:

**Who acts → what they touch → what changes → how the character reacts → where the brand appears.**

Character actions should trigger on-screen changes. For example, the croissant shopkeeper pulls a paper strip and the shop unfolds; bread lands on a tray, then into a takeaway bag printed with the shop name. If the story is exactly the same with the character removed, redesign the character's role. Product shots do not need a forced character, but shots the character appears in must give it a clear purpose.

Give each segment one main mechanism, usually 3–6 groups of large objects to convey one idea. Fix the finished composition, 2–4 key poses and prop ownership first, then build the in-between process. Do not replace item-by-item entry, lock-in, trigger and result with a whole-frame fade, slow zoom or aimless drift. Object counts are readability guidance, not a hard limit for every ad.

## Division of labor between the two methods

- **Character production:** reuse the identity reference and fix silhouette, costume construction, material and lighting; the face, head, torso and relevant limbs act together, retaining anticipation, exertion, reaction and settling. Consecutive poses share one crop and scale — follow [the action stability checks](stability.md) and [clarity handling](clarity.md).
- **Collage storytelling:** turn one sentence into a readable action relationship; set the end state first, then plan where paper pieces enter from, how they connect and how they complete the change. Unify color, paper edges and shadows; do not pack the frame with fragments.
- **Scene composition:** align the character action's trigger point, prop changes, contact points, copy and sound. Keep characters, products, packaging and text on separately editable layers.

A usable shot record:

| What to record | Bakery example |
| --- | --- |
| One-sentence idea | Slowly open today |
| Who acts, what they touch | The croissant reaches for the paper strip and pulls back |
| Key moments | Grab → pull → three-fold shop unfolds → show the result |
| Prop ownership and occlusion | The paper strip links the hand and the shop; character in front, shop behind |
| Brand placement | The shop name appears on the signboard after unfolding |

Fix the story and visuals first, then produce the more expensive animation. For unproven new character actions, make a sample first; when the user has accepted the direction, asked to continue or directly requested the film, carry that authorization forward instead of repeating the same round of confirmation.

## Choosing the implementation

When brand text, object counts, grips, occlusion and later edits need precise control, prefer an editable layered composite. The existing pose exporter scripts produce character assets; they do not run the ad timeline themselves — choose a video compositor that actually works in the target environment. If HyperFrames is used, follow its current production notes and check flow; do not copy any specific, easily outdated version's install steps here.

When using video generation, pin down the confirmed start state, end state and action order, and check whether the middle adds, loses or replaces objects. Keep the user's chosen tools and models; borrowing a collage method does not automatically bind a model or require a new service. A layered composite can also achieve paper-assembly storytelling.

Do not redraw every accepted character for an ad; add only genuinely missing actions or props. The same character assets can be reused for separate chat GIFs, social media or shop material, but that is extra delivery, arranged at the user's request; the same action with a few different captions does not count as multiple new actions.

## Brand placement

Place the brand into story objects: packaging bags, cup sleeves, menus, signboards, labels or the product itself. By default use only brand information the user provides or explicitly marks as fictional. Leave enough reading time at the end for the shop name and invitation line; check against the actual character count, canvas and phone size, and do not treat the bakery sample's seconds as the default for all projects.

Respect the user's specified aspect ratio, duration, music and copy requirements. Without explicit specs, make a reasonably scoped sample, then decide dimensions by use; the GIF's 512px canvas and roughly two-second loop do not automatically apply to a brand film.

## Continuity checks and the actual-film review

Track every object at every moment: whose hand it is in, where it sits, whether it brings its own container, and whether it is in the foreground or background.

- **Action and result:** the trigger precedes the result, the character anticipates and reacts, and contact points follow the action.
- **Object ownership:** whether the hand grips the prop, the foot lands on the ground, the food lands in the right place. The same tray of bread must not bring a plate of its own and then stack onto another.
- **Occlusion and edges:** check front/back packaging layers, the character peeking out, the bag opening, moving crop boundaries and enter/exit moves. Do not inspect only the static final frame.
- **Shot continuity:** whether counts, positions, sizes and movement directions line up across a transition; intentional jump cuts must read clearly.
- **Output and sound:** check the actual exported video, around the key actions and the last second, confirming no obvious frame skipping, face morphing, text clipping or audio-video desync. Verify duration, dimensions, frame rate, audio track and that the file opens; when sound was only measured, do not claim it was auditioned.

Keep the original version; patch the specific faulty prop, pose or layer, then re-check the affected process. Do not regenerate a whole shot over one plate, and do not mask missing action transitions by adding frame rate.

## Deliverables and verified cases

Deliver the film, the editable project and necessary source credits/attribution; check that the project archive extracts, referenced assets are complete and paths are portable. Standalone character GIFs are extra delivery only within the agreed scope. Distinguish generated pose animation, layered compositing and true 3D animation; do not promise unverified stability.

This repo's [Manman Bakery case](../examples/brand-films/manman-bakery/README.md) includes a 15-second film, an animated preview, an editable project and action GIFs. The user accepted this fusion test film and asked for publication; that is confirmation of this specific sample, not a guarantee that new brands, new characters and every generation will be stable. The film is a clay-look pose sequence plus layered compositing, without Gemini video scripting. The strip contact is approximate alignment, and the bread entering the next shot uses an anthropomorphic toss.

## Method provenance

The visual proposition, small-object assembly and start/end-state design reference [gbro-collage-broll](https://github.com/pyang5166/gbro-collage-broll). This workflow rearranges them in combination with this repo's existing character-action, clarity and stability checks; it does not copy that project's approval protocol or fixed-model requirements. If that Skill is actually invoked, read its current instructions and honor the user's authorization and tool choices for the task at hand.
