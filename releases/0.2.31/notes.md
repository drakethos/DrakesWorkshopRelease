# Drake's Workshop 0.2.31

Released: 2026-08-17T23:57:08Z

## License (Alpha optional)

Play in **Light** with no key. A **DWK-** key upgrades to **Alpha** (extra packs, Realistic terrain, more characters, upcoming hosting).
Recover: https://api.hauskode.com/recover - Apply: https://drakesworkshop.net/play?apply=1

## Install (preferred)

1. Download **DrakesWorkshop-0.2.31-Full-Setup.msi** from the [GitHub Release](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.2.31) or https://drakesworkshop.net/download
2. **DrakesWorkshop-0.2.31-Full-Setup.msi** installs to Program Files (admin). The .exe is a per-user LocalAppData install.
3. Setup installs Core **and content** (meshes, music, skies, worlds). First launch finishes extracting bundled packs, then the game starts.
4. Play in Light. Optional: Unlock Alpha... and enter your DWK- key

Requires the **.NET 8** runtime (Setup can install it).

## Updates

Quit and relaunch. Auto-update downloads **slim Core only** (`DrakesWorkshop-win-Setup.exe` / nupkg) -- not another full content installer. Missing or newer packs come from the content feed.

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-0.2.31-Full-Setup.msi | 99.3 MB | `af149975fea06c17fca15e0b240faaee90c37857f10ee22f2810efdf2933e0b7` |
| DrakesWorkshop-0.2.31-Full-Setup.exe | 114.5 MB | `911d70dbf4974b5cfdfdd66f8dc63d3cd6dd6fa62342580e673bdbb97aa9aff9` |
| DrakesWorkshop-win-Setup.exe | 89.4 MB | `4309ca6e9d5e8872d2c88e85bd13ea78a3ea7b08a0bba4d6d6980fbadf8d7543` |

`DrakesWorkshop-0.2.31-Full-Setup.msi` is the download-page installer. Slim `DrakesWorkshop-win-Setup.exe` + nupkg is the auto-update channel. Content packs also ship from `drakesworkshop-lib-release` (rolling tag `content-latest`).

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### Fixed (0.2.31)
- **Content install no longer freezes the app.** Skipping a package (or the stall watchdog doing it for you) deleted the in-progress unpack folder on the main thread while the installer was still writing to it, which locked the window: the progress bar sat at 100% and Skip / Continue anyway / Quit all stopped responding. Cleanup now runs in the background and never blocks the UI.
- **Install progress shows it is working.** Unpack and file-copy report stage, files written, and elapsed time instead of a static "please wait", so a large pack that legitimately takes minutes no longer looks hung, and the watchdog stops cancelling healthy installs.
- **Always a way out.** The update overlay has a **Quit** button, and Skip dismisses the lock if the download queue already finished.
- Temp folders left behind by an interrupted or force-quit install are cleaned up on the next launch.

### Install (0.2.31)
- **Download what the map needs:** worlds stamp `asset_deps`; Play / Host / Join pull missing **Light** packs before launch. Alpha-only deps stay behind a DWK- upgrade prompt.
- Quiet boot still hydrates **Light essentials** only; Misc -> Check for updates pulls the rest.

### Build
- Friend build **0.2.31** - content-install freeze fix on the **0.2** friend track

See [CHANGELOG.md](../CHANGELOG.md).
