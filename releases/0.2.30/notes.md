# Drake's Workshop 0.2.30

Released: 2026-08-17T02:48:53Z

## License (Alpha optional)

Play in **Light** with no key. A **DWK-** key upgrades to **Alpha** (extra packs, Realistic terrain, more characters, upcoming hosting).
Recover: https://api.hauskode.com/recover - Apply: https://drakesworkshop.net/play?apply=1

## Install (preferred)

1. Download **DrakesWorkshop-0.2.30-Full-Setup.msi** from the [GitHub Release](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.2.30) or https://drakesworkshop.net/download
2. **DrakesWorkshop-0.2.30-Full-Setup.msi** installs to Program Files (admin). The .exe is a per-user LocalAppData install.
3. Setup installs Core **and content** (meshes, music, skies, worlds). First launch finishes extracting bundled packs, then the game starts.
4. Play in Light. Optional: Unlock Alpha... and enter your DWK- key

Requires the **.NET 8** runtime (Setup can install it).

## Updates

Quit and relaunch. Auto-update downloads **slim Core only** (`DrakesWorkshop-win-Setup.exe` / nupkg) -- not another full content installer. Missing or newer packs come from the content feed.

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-0.2.30-Full-Setup.msi | 99.3 MB | `38c5fd761b83282ecbc741545bededb926cf2e0656837d479b097d095036aa90` |
| DrakesWorkshop-0.2.30-Full-Setup.exe | 114.5 MB | `43a0379d58812e7a911e07343c132c78418ad3170dabf727b1cda525e4e0894b` |
| DrakesWorkshop-win-Setup.exe | 89.4 MB | `6503700f009a5b43902073336fe2947ddb6b76baf2eb811f4d3e763b6f54e03d` |

`DrakesWorkshop-0.2.30-Full-Setup.msi` is the download-page installer. Slim `DrakesWorkshop-win-Setup.exe` + nupkg is the auto-update channel. Content packs also ship from `drakesworkshop-lib-release` (rolling tag `content-latest`).

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### Install (0.2.30)
- **Smaller mesh packs:** unused Godot-extracted PNG sidecars are gone from self-contained GLBs (`fantasy_props`, `stylized_nature`, `universal_chars`, and medieval village in-repo). Runtime already used the embedded textures.
- **Download what the map needs:** worlds stamp `asset_deps`; Play / Host / Join pull missing **Light** packs before launch. Alpha-only deps stay behind a DWK- upgrade prompt.
- **More reliable content downloads** in exported builds (system curl instead of Godot HTTP).
- Quiet boot still hydrates **Light essentials** only; Misc â†’ Check for updates pulls the rest.

### Build
- Friend build **0.2.30** â€” pack sidecar strip, native-curl content client, and world `asset_deps` on the **0.2** friend track

See [CHANGELOG.md](../CHANGELOG.md).
