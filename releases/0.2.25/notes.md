# Drake's Workshop 0.2.25

Released: 2026-08-13T18:59:48Z

## License (Alpha optional)

Play in **Light** with no key. A **DWK-** key upgrades to **Alpha** (extra packs, Realistic terrain, more characters, upcoming hosting).
Recover: https://api.hauskode.com/recover - Apply: https://drakesworkshop.net/play?apply=1

## Install (preferred)

1. Download **DrakesWorkshop-win-Setup.exe** from the [GitHub Release](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.2.25)
2. Run the installer (Start Menu + Desktop shortcuts)
3. Launch Drakes Workshop -- launcher checks **GitHub Releases** for updates on every start
4. Play in Light. Optional: Unlock Alpha... and enter your DWK- key

Requires the **.NET 8** runtime (Setup can install it).

Auto-update: Velopack GithubSource -> `https://github.com/drakethos/DrakesWorkshopRelease` (nupkg + RELEASES on this tag).

## Portable (optional)

### First time
1. Download **DrakesWorkshop-0.2.25-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) - Light needs no key. Unlock Alpha... to enter a DWK- key

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.25-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 89.2 MB | `5da6f035c4c83b5f843c2cf6b270c6c6550520ba50c5986435cd65e28d7674c8` |
| DrakesWorkshop-0.2.25-Windows.zip | 80.7 MB | `b75f9523814903a1d7d930315e99306477d1712aa9b5ddb52275d6bc03813e7d` |
| DrakesWorkshop-0.2.25-Update.zip | 11 MB | `1338f8b0a8e242d71267261e45a69afd10156ce1d9764e0723f52b075925b62c` |

Velopack feed (`*.nupkg`, `releases.win.json`) is attached to this GitHub Release. Content packs ship from the separate `drakesworkshop-lib-release` repo (rolling tag `content-latest`).

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### New
- **Light** play with no key; optional **`DWK-`** Alpha upgrade (extra packs, Realistic terrain, more characters, upcoming hosting)
- Robots Can't Swim team skins + magenta-key tint path
- Official world / lobby Lua updates (`dont_drown`, player management)

### Fixes
- Public README + release notes match Light (no longer imply a key is required to boot)

### Build
- Friend build **0.2.25**  -  Core patch on the **0.2** friend track
- Systems: **core 0.1.4** (player_management); platform/sandbox **0.1.4**, adventure **0.1.2**, rpg/rts **0.1.0**
- Official worlds stamped for Core **0.2.25** (RCS **0.1.7**, sandbox/lava **0.1.1**)
- Wave A / **0.3.0** still waits on Direct Connect dogfood

See [CHANGELOG.md](../CHANGELOG.md).
