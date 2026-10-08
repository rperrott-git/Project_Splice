# Art Direction

## Creator's art — OBSERVED
The creator supplied four original example creature sprites (`art_references/`). They feature very low-resolution, chunky pixel shapes, concise palettes and bold silhouettes. These are the visual starting point and should inform monster proportions and project scope.

## Preferred approach — AGREED DIRECTION
Stylized **2.5D / Paper Mario-like** presentation: flat pixel-art creature sprites in dimensional environments. The creator is comfortable drawing back-facing and side-facing variants, enabling more dynamic battle cameras. Consider fixed or controlled three-quarter camera angles and a pulled-back side-selection view with closer row-attack framing.

## Practical animation — PROPOSAL
Three base orientations per species (front, back, side; mirror side if appropriate). Animate with modest engine transforms (bob, tilt, lunge, squash/stretch), occasional small custom frames, pixelated effects and shadows. Prioritize readable combat over a high frame count. Prevent subpixel shimmer through sprite filtering/pixel snapping/camera choices.

## Battle readability — OPEN
Two rings of up to 16 allied creatures (and opponent formations) can crowd the screen. Prototype actual sprite scale, camera angles, occlusion, foreground/background distinction, elemental highlights, front/rear HP/MP indications, and lane-break indicators before committing to art production.

## Environment — DIRECTION
Dungeons likely top-down or three-quarter pixel-art exploration with a separate dimensional battle arena. Low-poly/storybook environmental treatment is a potential complement, not finalized. The final artistic treatment must respect original chunky sprite style rather than imposing arbitrary higher resolution.

## Production guardrails
Avoid requiring procedurally merged monster sprites for every DNA combination. A splice usually retains recipient species and artwork; alternate palettes or variants can represent rare biology. Prioritize diverse silhouettes and clear visual states.

## Open
Exact sprite resolutions, target display resolution, interpolation/pixel scale, tile size, engine, rendering pipeline, exploration camera, UI art, lighting/shader style, animation effort.