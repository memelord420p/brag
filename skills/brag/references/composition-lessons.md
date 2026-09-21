# Brag composition lessons (theblankofblank / HyperFrames)

Lessons from shipping a portrait + landscape brag for a dark map product UI. Bake these into `/brag` runs so the next video is faster and cleaner.

## Opening brand beat

- Do **not** hang on the wordmark alone for 2–3s.
- After the mark lands (~0.2–0.3s), bring in a short product line under it within ~1s (e.g. **Navigate by familiarity.**).
- Exit the whole stack together (~2.5s). Brand first, meaning second — never a dead logo hold.

## Readability on phone (vertical)

- Punching into tiny UI chrome is not enough. Prefer **text-first giant callout cards** over the dimmed product shot for key claims.
- Keep type huge: neighborhood name ≥ ~64–72px on 1080×1920; supporting line still legible at arm’s length.
- Dim the underlying screenshot (`filter` + scrim) so overlays read as the hero.

## Cursor / click beats

- If you zoom the product shot, put the **cursor outside** the scaled stage (high `z-index` sibling), or the cursor disappears into the crop.
- Make the cursor large (≈40–56px), animate toward the CTA, press scale, and fire a **ripple** + click SFX.
- Soften pick-stage zoom so the tap target stays on-frame.

## Map UIs with a baked-in sidebar

Static app screenshots often include a left list panel. **Panning the whole stage cannot clear that bar** — you are sliding the sidebar with the map.

**Do this instead:**

1. Prefer **one screenshot per selected area** (map already flown to that neighborhood) and crossfade between shots with matching callouts.
2. Or **reframe the shot** so the sidebar is off-canvas (`#map-shot` wider + negative `left`, `object-position: right`) and only the map pane fills the frame, then pan within that map-only crop.
3. Sync neon hotspot rings (color = product neighborhood color) to each callout beat; pulse the ring while the card is up.

Never assume translateX will “move the highlight out from under” a baked sidebar.

## Hotspot / callout sync

- Use `autoAlpha` (not bare `opacity`) for callouts that start hidden.
- Prefer solid `rgba(...)` over `color-mix` for Chromium render reliability.
- Timeline: pan → hotspot pop (`back.out`) → callout in → callout out / hotspot dim → next area.

## Dual format

Ship **portrait and landscape** compositions with the same story beats. Landscape can keep more of the product chrome; portrait should lean harder on overlays.

## Audio

- Keep a quiet bed under VO-free brags; duck slightly under dense UI moments if needed.
- Click / select / drop SFX on pick + each map beat + outro.

## QA checklist before final render

- [ ] Opening shows brand **and** tagline
- [ ] Cursor tap is visible on the pick beat
- [ ] Every named area has a visible map highlight **not** under chrome
- [ ] Portrait type readable on a phone screen recording
- [ ] `npx hyperframes check` clean; snapshot the callout timestamps
- [ ] Both aspect ratios rendered and spot-checked
