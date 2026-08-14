# Drake's Workshop 0.2.28

Released: 2026-08-14T00:49:53Z

## License (Alpha optional)

Play in **Light** with no key. A **DWK-** key upgrades to **Alpha** (extra packs, Realistic terrain, more characters, upcoming hosting).
Recover: https://api.hauskode.com/recover - Apply: https://drakesworkshop.net/play?apply=1

## Install (preferred)

1. Download **DrakesWorkshop-0.2.28-Full-Setup.msi** from the [GitHub Release](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.2.28) or https://drakesworkshop.net/download
2. **DrakesWorkshop-0.2.28-Full-Setup.msi** installs to Program Files (admin). The .exe is a per-user LocalAppData install.
3. Setup installs Core **and content** (meshes, music, skies, worlds). First launch finishes extracting bundled packs, then the game starts.
4. Play in Light. Optional: Unlock Alpha... and enter your DWK- key

Requires the **.NET 8** runtime (Setup can install it).

## Updates

Quit and relaunch. Auto-update downloads **slim Core only** (`DrakesWorkshop-win-Setup.exe` / nupkg) -- not another full content installer. Missing or newer packs come from the content feed.

## Portable (optional)

### First time
1. Download **DrakesWorkshop-0.2.28-Full-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) - Light needs no key. Unlock Alpha... to enter a DWK- key

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.28-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-0.2.28-Full-Setup.msi | 1506.7 MB | `88978d222c3bc2c9926bce319760865149389339b3c489921b862eb42c2e4f17` |
| DrakesWorkshop-0.2.28-Full-Setup.exe | 1520.7 MB | `ce6577bfcce095d53d4c7aa50c9a4fff0f0116d619f9a50336c72fa8cc672424` |
| DrakesWorkshop-win-Setup.exe | 89.3 MB | `b47019ae6cb194629b61a5f79a250e6fefc13b7d9aa37d3a83291f206233d45b` |
| DrakesWorkshop-0.2.28-Windows.zip | 80.7 MB | `44cd9caf9875d62105df37f3d64abe5c9c33e9fff54fb57ef507a57c9cf7adb1` |
| DrakesWorkshop-0.2.28-Update.zip | 11 MB | `5c54496e46b1b438787f51e7a32d9567f4b1197b2925e22ed360246ef9eaf208` |
| DrakesWorkshop-0.2.28-Full-Windows.zip | 1512.1 MB | `4bc50eccb8f8157011d6adaccf833c5cfd647ee696e4a96147f7fd7cb7dd1340` |

`DrakesWorkshop-0.2.28-Full-Setup.msi` is the download-page installer. Slim `DrakesWorkshop-win-Setup.exe` + nupkg is the auto-update channel. Content packs also ship from `drakesworkshop-lib-release` (rolling tag `content-latest`).

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### Install (0.2.28)
- **Kenney skins:** Full Setup and the content feed now keep `Textures/` atlases (character skins, town/building colormaps). Older packs that shipped GLBs only are treated as incomplete and re-pulled.
- **First install:** `DrakesWorkshop-*-Full-Setup.msi` (Program Files) or `.exe` (per-user) still hydrates content on first launch.
- **Updates:** slim Velopack nupkg (Core only). Missing packs come from the content feed.

### Build
- Friend build **0.2.28** â€” Kenney texture packing fix on the **0.2** friend track

See [CHANGELOG.md](../CHANGELOG.md).
