# Skate 3 clean room (web)

Play: **https://duckywarex.github.io/skate3-cleanroom/** (Chrome or Edge 113+ with WebGPU)

This is the Skate 3 Rust/Bevy engine rewrite ([skate-3-rust-engine](https://github.com/andrewnakas/skate-3-rust-engine), branch `cleanroom-web`) compiled to WebAssembly + WebGPU. It runs on a **clean asset pack**. Every image, every sound and every visual mesh in the pack was regenerated, so no retail pixels, samples or mesh buffers are shipped.

## What the pack contains

| Kind | Treatment |
|---|---|
| Textures (maps, props, backdrops, skies, HUD, skater model): 7681 in total | **Regenerated.** Each one is rebuilt from its size, a 4x4 or 16x16 colour grid and a 2-bit alpha outline, plus our own detail noise and dither. |
| Visual geometry (maps, props, backdrops, skater model) | **Regenerated** (`geom.py`). Collision triangle values kept exactly; retail mesh buffers are not shipped. |
| Collision | Triangle positions, edge codes and surface ids are **kept exactly** (the skating depends on them). |
| Grind rails, spawns/teleports, skater skeleton | Kept (facts) |
| Animations, state graphs, physics/VLT tuning, input/camera configs | Kept (facts) |
| Player sound effects | **Regenerated** from coarse outlines (`audio_clean.py`). |
| Music, speech | Not shipped. |
| Everything else from the disc | Dropped |
| `dmjumpline` map | Author's own map; shipped and taint-scanned. |

## Controls

Keyboard maps to an Xbox-style pad:

| Action | Keys |
|--------|------|
| Left stick | WASD |
| Right stick (flick-it) | Arrow keys |
| A (push) | Space |
| B / X / Y | E / Shift / F |
| Triggers | Z / C |
| Bumpers | Q / R |
| Start | Enter |

Browser gamepads work directly. Change maps with the picker (bottom right), or use `?map=Name` in the URL.

## Community maps

- **skatemods.com**: `?smap=<map id>`
- **Any CORS-readable URL**: `?mapurl=https://.../park.skate`
- **Local file**: "Open .skate file..." in the picker

## Known limits

- Needs **WebGPU** (Chrome or Edge 113+).
- Large districts (DownTown, University, Industrial) may not fully render on web yet.
- First load downloads engine + core pack (roughly 150 MB+).

## License / legal

Unofficial fan project. Not affiliated with Electronic Arts. No retail Skate 3 assets are distributed.
