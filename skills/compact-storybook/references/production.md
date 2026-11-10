# Production and review

## State continuity

Record per page: page number, background, characters, start state, main action, end state, prop holder/count, and how the next page continues it.

Example: a blue-grey sheet of paper handed by the bear to the girl → folded into a paper bird → set free → caught by the fox → unfolded to read the letter. This is one prop changing form; a second bird must not appear when it lands. After the fox hands the leaf to the bear, the next page must not still hold the same leaf.

Pages may switch environment and composition, linked by the same object, action result or eyeline; do not pad with long walking transitions to fake continuity, and do not switch to a wide/close/reverse shot sequence on your own.

## Pose-sheet assembly

- The background contains none of the characters or moving props composited in this pass, preventing ghosts and duplicated objects.
- A single action can start from 8–12 drawn key poses distributed over about 18 output frames; the pose count and holds are set by the action, not by equal timing.
- Fix the canvas, camera, scale and cell layout; inspect cell by cell for wrong faces, changing clothes, extra hands and prop jumps. A missing cell must not skip the key contact action.
- Use one shared alpha crop, a common scale and a stable foot baseline for all poses. Do not tight-crop each frame individually and fill the cell, or the figure will grow and shrink and the feet will drift. Nearest-neighbour scaling for pixel art only; keep anti-aliasing for illustration.
- Decode all assets before registering a seekable deterministic timeline where each frame is computed from time — not from live timing, unfixed randomness or network response order.

## Contact and occlusion

Held items use each pose's palm anchor; resting items use tabletop/floor anchors. A flying item's endpoint meets the landing-hand anchor, and after being caught it moves with the hand — it must not keep drifting along an independent path.

Separate chair/background, body, hands and held items, and tabletop edge. Redrawing the whole background outright clips hands and cups, so check pose by pose. On putting down, switch from the held layer to the resting layer, appearing exactly once.

Observed problems: the paper bird landed below the hand; a cup reused chest coordinates and floated after being put down. Fix the actual anchors and occlusion; do not force the previous coordinates onto a new character.

## Compact pacing

Starting point for a 3s page: about 0.2–0.4s to establish the pose, about 1.5–2s to complete the action, about 0.5–1s to read the result. A complex action may run longer or split into two pages; do not cram it into 3s.

N pages, d seconds each, p seconds per page turn: total length `N*d+(N-1)*p`. The accepted case is 12×3+11×0.5=41.5s, four chapters of three pages = 10s each; case specs only.

A 0.5s page turn at 6fps is only 3 frames; check the page flip is still recognizable. The book frame must not cover the action. When the user wants standalone animation, no book frame; do not raise only the outer layer to 30fps and still call the whole file 6fps.

## Acceptance and sharing

Run the current renderer's checks in the project directory. One root entry, other entries in subdirectories, to avoid conflicting multiple root entries; take exact commands from the current help and skill, not copied from an older version.

Check the actually decoded first/middle/last frames, before and after hand-offs, before/middle/after page turns, and text at phone size. A Canvas may be falsely flagged as static by a static check; record it as a false positive only after confirming with actual frame changes.

Silence is only the previous sample's state, not a hard requirement for every story. Handle sound per the user's needs and authorization; when music is missing, deliver the action version first with a note that it is silent; do not silently promise the music is done.

Record specs, check results and unconfirmed art quality. Passing the checks does not mean the user is satisfied. Before sharing a project, remove private paths, source images and unused assets; do not package fonts without distribution rights — swap in licensed fonts or provide substitution instructions.
