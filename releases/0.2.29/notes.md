# Drake's Workshop 0.2.29

Released: 2026-08-14T02:19:01Z

## License (Alpha optional)

Play in **Light** with no key. A **DWK-** key upgrades to **Alpha** (extra packs, Realistic terrain, more characters, upcoming hosting).
Recover: https://api.hauskode.com/recover - Apply: https://drakesworkshop.net/play?apply=1

## Install (preferred)

1. Download **DrakesWorkshop-0.2.29-Full-Setup.msi** from the [GitHub Release](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.2.29) or https://drakesworkshop.net/download
2. **DrakesWorkshop-0.2.29-Full-Setup.msi** installs to Program Files (admin). The .exe is a per-user LocalAppData install.
3. Setup installs Core **and content** (meshes, music, skies, worlds). First launch finishes extracting bundled packs, then the game starts.
4. Play in Light. Optional: Unlock Alpha... and enter your DWK- key

Requires the **.NET 8** runtime (Setup can install it).

## Updates

Quit and relaunch. Auto-update downloads **slim Core only** (`DrakesWorkshop-win-Setup.exe` / nupkg) -- not another full content installer. Missing or newer packs come from the content feed.

## Portable (optional)

### First time
1. Download **DrakesWorkshop-0.2.29-Full-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) - Light needs no key. Unlock Alpha... to enter a DWK- key

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.29-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-0.2.29-Full-Setup.msi | 1454.3 MB | `4dc17934e5f4d4032d5ce42d207fb00f49254088688665d16a77656ee59249d1` |
| DrakesWorkshop-0.2.29-Full-Setup.exe | 1468.5 MB | `89b8bf5caceb6e994cc7ce2f665a110fec13d8a1fa28307e78e17dbf77192c60` |
| DrakesWorkshop-win-Setup.exe | 89.4 MB | `becb69ab6f4aa0ffa4a14989ea3dd39462027dcfafccf1848b97243acc69eb70` |
| DrakesWorkshop-0.2.29-Windows.zip | 80.8 MB | `411552897be471cec9d21307e5d598f133cec42d81d23625f1d8122c52df4a16` |
| DrakesWorkshop-0.2.29-Update.zip | 11 MB | `adf9b56ec708e38c21b0fbc23ced17c7c560f915ddf78e8cf9acb25f77eb88fd` |
| DrakesWorkshop-0.2.29-Full-Windows.zip | 1459.8 MB | `6b38bc9c81a3ce2c5b0b91c9d9dc9d2b1b98548fd9faf3659e8ef6a0362135f2` |

`DrakesWorkshop-0.2.29-Full-Setup.msi` is the download-page installer. Slim `DrakesWorkshop-win-Setup.exe` + nupkg is the auto-update channel. Content packs also ship from `drakesworkshop-lib-release` (rolling tag `content-latest`).

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### Install (0.2.29)
- **Smaller downloads:** content-feed packs are zstd-framed (filenames stay `*.zip`). Older DEFLATE seeds still install.
- **Optional packs stay in the repo** but are omitted from Full Setup / the feed until flipped on: marble, extra Kenney player kits (`mini_chars`, `anim_chars`), Quaternius players (`universal_chars`), unused weapons (`medieval_weapons`). Toggle in `tools/release/content-pack-deploy.json`.
- **First install:** `DrakesWorkshop-*-Full-Setup.msi` (Program Files) or `.exe` (per-user) hydrates content on first launch.
- **Updates:** slim Velopack nupkg (Core only). Missing packs come from the content feed.

### Build
- Friend build **0.2.29** â€” zstd content archives + deploy skip list on the **0.2** friend track

See [CHANGELOG.md](../CHANGELOG.md).
