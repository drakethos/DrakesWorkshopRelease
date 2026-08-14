# Drake's Workshop 0.2.27

Released: 2026-08-14T00:00:35Z

## License (Alpha optional)

Play in **Light** with no key. A **DWK-** key upgrades to **Alpha** (extra packs, Realistic terrain, more characters, upcoming hosting).
Recover: https://api.hauskode.com/recover - Apply: https://drakesworkshop.net/play?apply=1

## Install (preferred)

1. Download **DrakesWorkshop-0.2.27-Full-Setup.msi** from the [GitHub Release](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.2.27) or https://drakesworkshop.net/download
2. **DrakesWorkshop-0.2.27-Full-Setup.msi** installs to Program Files (admin). The .exe is a per-user LocalAppData install.
3. Setup installs Core **and content** (meshes, music, skies, worlds). First launch finishes extracting bundled packs, then the game starts.
4. Play in Light. Optional: Unlock Alpha... and enter your DWK- key

Requires the **.NET 8** runtime (Setup can install it).

## Updates

Quit and relaunch. Auto-update downloads **slim Core only** (`DrakesWorkshop-win-Setup.exe` / nupkg) -- not another full content installer. Missing or newer packs come from the content feed.

## Portable (optional)

### First time
1. Download **DrakesWorkshop-0.2.27-Full-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) - Light needs no key. Unlock Alpha... to enter a DWK- key

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.27-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-0.2.27-Full-Setup.msi | 1506.1 MB | `8a8c250f336cfade63ccb896ff700eff59bbfddb0edaeb0aee9cb2e5129dbb8b` |
| DrakesWorkshop-0.2.27-Full-Setup.exe | 1520 MB | `be9e1b9b0d5a358b341bae6b3b1d14de1d3db0c0244485f0ae2ab3640173c7e1` |
| DrakesWorkshop-win-Setup.exe | 89.3 MB | `f4c356489d2fa01a7187b6bc84934349e4f300b8c5b8fa7bc0ce50f39fd06ae7` |
| DrakesWorkshop-0.2.27-Windows.zip | 80.7 MB | `4944993682c439dad3a23670d7d535f88bad44b186a2a0be5c79ff20435484f5` |
| DrakesWorkshop-0.2.27-Update.zip | 11 MB | `0cf33a4cd1dc184f6670c19c5017bd6df46d3f5d07ff50cf736d2d40902debef` |
| DrakesWorkshop-0.2.27-Full-Windows.zip | 1511.4 MB | `83b62db55d1c6cc7bb4a0c206bccfe536cc9804ce693678acd7e80c39f2b447f` |

`DrakesWorkshop-0.2.27-Full-Setup.msi` is the download-page installer. Slim `DrakesWorkshop-win-Setup.exe` + nupkg is the auto-update channel. Content packs also ship from `drakesworkshop-lib-release` (rolling tag `content-latest`).

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### Install (0.2.27)
- **First install (download page):** `DrakesWorkshop-*-Full-Setup.msi` installs to **Program Files** (admin) with Core **and content**. The `.exe` is the per-user Local AppData Full Setup.
- **Content is installed on first launch:** the launcher extracts bundled packs (meshes, music, skies, worlds, Systems) before the game starts â€” no content-feed grab on a fresh Full Setup.
- **Updates:** slim Velopack nupkg (Core only). Missing or newer packs come from the content feed.

### Build
- Friend build **0.2.27** â€” Full Setup + Program Files MSI on the **0.2** friend track

See [CHANGELOG.md](../CHANGELOG.md).
