# Nine Lenticular Cards (电子光栅卡): examples and sources

All nine characters are now in place: Spider-Man (蜘蛛侠), Ghost Rider (恶灵骑士), Venom (毒液), Iron Man (钢铁侠), Batman (蝙蝠侠), Black Panther (黑豹), Wolverine (金刚狼), Captain America (美国队长) and Deadpool (死侍).

Each standalone GIF is 480×720, 6 seconds, looping forever. Made by sampling at 20fps, with repeated hold frames merged at encode time; after decoding there are usually 32 frames, and hold time counts inside the 6 seconds. The nine-grid overview pulls frames by time so that every card plays at a consistent pace. The original four are direct copies of the confirmed versions; Spider-Man uses the first version the user specified, not swapped for a later narrow-format or stitched version.

Image generation for the five added characters was blocked by the service, so all five ended up using ready-made assets found online; failed requests were not recorded as successes. Black Panther is a digital painting and Wolverine a vector illustration; other assets include composites too, so this set is not all live-action film stills or a single drawing style.

## Sources and production methods

|Character|Source|Production method|
|---|---|---|
|Spider-Man|[TMDB backdrop](https://www.themoviedb.org/movie/558-spider-man-2/images/backdrops)|Original confirmed version: face-splice image cropped per side, mask side mirrored|
|Ghost Rider|User-provided composition reference, generated with the built-in image tool|Completed half-face close-up version|
|Venom|User-chosen Spider-Man image as composition reference, generated with the built-in image tool|Completed version|
|Iron Man|[Asset discovery page](https://in.pinterest.com/pin/53972895529068863/)|Completed version; ready-made face-splice asset|
|Batman|[IMDb article page](https://www.imdb.com/news/ni65026701/)|Two ready-made photos paired; face and mask cropped, mirrored and aligned by eye position and chin|
|Black Panther|[Digital painting discovery page](https://www.pinterest.com/pin/129548926768266538/)|Author not yet verified; the left/right halves of a ready-made digital painting are used; the source original is kept in the production directory|
|Wolverine|[Daniel Vásquez: Wolverine/Hugh Jackman Vector](https://www.behance.net/gallery/120626151/WolverineHugh-Jackman-Vector)|Uses his vector illustration; one half cropped and mirrored, keeping the painterly texture|
|Captain America|[Asset discovery page](https://pantip.com/topic/35110484/desktop)|Ready-made face/mask composite; greyscale mask with a colour face|
|Deadpool|[Asset discovery page](https://www.pinterest.com/pin/45106433746532302/)|Ready-made actor/character face-splice composite; greyscale actor with a red mask|

These are dynamic-effect samples; commercial-use authorization for the web assets and character IP has not been verified. Source pages are for tracing, not evidence of licensing. The Wolverine original belongs to Daniel Vásquez; the other ready-made originals belong to their respective authors/rights holders.

The output includes nine standalone GIFs, the nine-grid animated overview, a static overview and verification results. Each card keeps its own material and background; no side strips are artificially spliced onto the frames.


## View and download

[Animated overview](preview.gif) · [Nine standalone GIFs (zip)](cards.zip) · [State A](state-a.jpg) · [State B](state-b.jpg) · [Actual decode check](review.json)

Usage conditions, failure handling and redo criteria are in [the Lenticular Card process](../../references/lenticular.md). Abandoned versions — the narrow format, the large black right-hand bar, the hard-spliced city shot and the Polaroid photo wall — are not included here.
