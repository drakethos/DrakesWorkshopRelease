# Drake's Workshop 0.3.2.0

Released: 2026-10-12T15:25:48Z

## License (Alpha optional)

Play in **Light** with no key. A **DWK-** key upgrades to **Alpha** (extra packs, Realistic terrain, more characters, upcoming hosting).
Recover: https://api.hauskode.com/recover - Apply: https://drakesworkshop.net/play?apply=1

## Install (preferred)

1. Download **DrakesWorkshop-0.3.2.0-Full-Setup.msi** from the [GitHub Release](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.3.2.0) or https://drakesworkshop.net/download
2. **DrakesWorkshop-0.3.2.0-Full-Setup.msi** installs to Program Files (admin). The .exe is a per-user LocalAppData install.
3. Setup installs Core **and content** (meshes, music, skies, worlds). First launch finishes extracting bundled packs, then the game starts.
4. Play in Light. Optional: Unlock Alpha... and enter your DWK- key

Requires the **.NET 8** runtime (Setup can install it).

## Updates

Quit and relaunch. Auto-update downloads **slim Core only** (`DrakesWorkshop-win-Setup.exe` / nupkg) -- not another full content installer. Missing or newer packs come from the content feed.

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-0.3.2.0-Full-Setup.msi | 99.7 MB | `ee478a390405cb1fa1b0740402d39ad37d142c8090b52809a8b6637397c5db6f` |
| DrakesWorkshop-0.3.2.0-Full-Setup.exe | 114.9 MB | `9914a6f08ade52963ff14f2c9d9da726836d0902e5540dc64b5a9926d743b374` |
| DrakesWorkshop-win-Setup.exe | 89.9 MB | `fc6972fd566055f6e31154cd2963c17a082e48e5858c92e5ba7b5c095fb2160d` |

`DrakesWorkshop-0.3.2.0-Full-Setup.msi` is the download-page installer. Slim `DrakesWorkshop-win-Setup.exe` + nupkg is the auto-update channel. Content packs also ship from `drakesworkshop-lib-release` (rolling tag `content-latest`).

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### Versioning (0.3.2.0)
- Core update on the 0.3.2 track (Velopack feed `0.3.200`). 0.4.0.0 is held for the online server.

### New
- **Tilesets:** one terrain system with swappable tilesets (Natural default, Cartoony, Autumn, Winter, High-end). A tileset picks the ground textures plus the grass, trees and rocks. Old Simple maps convert to Natural.
- **Scenery:** real 3D grass, flowers, trees, bushes, pebbles, stones and boulders painted on the ground (decoration, no collision), with Smart placement so things grow where it makes sense.
- **Seeded maps** now come with scenery; New Map has a separate Scenery option.
- **Cliffs:** sharp-edged Cliff up / down brush; terrain grid doubled to 64x64 (older maps convert on load).
- **Editor:** tabbed terrain tools (Sculpt, Paint, Cliffs, Water, Scenery), Smooth brush, one Graphics quality setting (Auto picks Low on integrated graphics).

### Fix
- Sculpting is far more responsive (the brush no longer re-copies the whole world each tick) and lands under the cursor on hills and pits.
- Maps no longer default to night: a missing or unknown sky is now day. The editor view stays bright daylight unless "Game lighting" is turned on.

### Build
- Core **0.3.2.0**. Environment assets (`assets/env`) ship in the runtime content pack, including the new tilesets and nature models.

See [CHANGELOG.md](../CHANGELOG.md).
