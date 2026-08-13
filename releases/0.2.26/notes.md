# Drake's Workshop 0.2.26

Released: 2026-08-13T21:07:57Z

## License (Alpha optional)

Play in **Light** with no key. A **DWK-** key upgrades to **Alpha** (extra packs, Realistic terrain, more characters, upcoming hosting).
Recover: https://api.hauskode.com/recover - Apply: https://drakesworkshop.net/play?apply=1

## Install (preferred)

1. Download **DrakesWorkshop-win-Setup.exe** from the [GitHub Release](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.2.26)
2. Run the installer (Start Menu + Desktop shortcuts)
3. Launch Drakes Workshop -- launcher checks **GitHub Releases** for updates on every start
4. Play in Light. Optional: Unlock Alpha... and enter your DWK- key

Requires the **.NET 8** runtime (Setup can install it).

Auto-update: Velopack GithubSource -> `https://github.com/drakethos/DrakesWorkshopRelease` (nupkg + RELEASES on this tag).

## Portable (optional)

### First time
1. Download **DrakesWorkshop-0.2.26-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) - Light needs no key. Unlock Alpha... to enter a DWK- key

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.26-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 89.3 MB | `27d750d45a20536461c44cc24be78beb16b5843a7079ccb84c60e8407794dd2f` |
| DrakesWorkshop-0.2.26-Windows.zip | 80.7 MB | `17f418fd0ee1f50ed5cb88034c2cb4850c1d5f7b3cf4aee47b1f702f4c72c309` |
| DrakesWorkshop-0.2.26-Update.zip | 11 MB | `350e948029ac9ed394e88bb0e5c6b10ad7144bffb3b95a0eb87b11ee5aa26723` |

Velopack feed (`*.nupkg`, `releases.win.json`) is attached to this GitHub Release. Content packs ship from the separate `drakesworkshop-lib-release` repo (rolling tag `content-latest`).

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### Important fixes (0.2.26)
- **White menu / missing meshes:** Slim Core does not ship pack meshes; missing packs fell back to white cubes
- **Locked content install:** Misc â†’ Check for updates (and boot auto-update) **locks the menu** with progress until packs finish â€” no more silent â€œAlready checkingâ€¦â€
- **Boot auto-update:** on launch, if the content feed has new Systems / worlds / runtime assets / **mesh packs**, install starts automatically under the lock overlay
- **Full Setup:** first-run offer + offline **Full Windows zip** with `content_seed` (recommended for first install)

### Install
- **Updates / everyday:** Velopack Setup.exe (slim Core; content pulls on launch)
- **First install (recommended):** `DrakesWorkshop-*-Full-Windows.zip` when attached (includes `content_seed`)

### Build
- Friend build **0.2.26** â€” emergency content-setup patch on the **0.2** friend track

See [CHANGELOG.md](../CHANGELOG.md).
