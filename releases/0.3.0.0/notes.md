# Drake's Workshop 0.3.0.0

Released: 2026-08-18T04:19:47Z

## License (Alpha optional)

Play in **Light** with no key. A **DWK-** key upgrades to **Alpha** (extra packs, Realistic terrain, more characters, upcoming hosting).
Recover: https://api.hauskode.com/recover - Apply: https://drakesworkshop.net/play?apply=1

## Install (preferred)

1. Download **DrakesWorkshop-0.3.0.0-Full-Setup.msi** from the [GitHub Release](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.3.0.0) or https://drakesworkshop.net/download
2. **DrakesWorkshop-0.3.0.0-Full-Setup.msi** installs to Program Files (admin). The .exe is a per-user LocalAppData install.
3. Setup installs Core **and content** (meshes, music, skies, worlds). First launch finishes extracting bundled packs, then the game starts.
4. Play in Light. Optional: Unlock Alpha... and enter your DWK- key

Requires the **.NET 8** runtime (Setup can install it).

## Updates

Quit and relaunch. Auto-update downloads **slim Core only** (`DrakesWorkshop-win-Setup.exe` / nupkg) -- not another full content installer. Missing or newer packs come from the content feed.

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-0.3.0.0-Full-Setup.msi | 99.3 MB | `49b0a6e46fb5e6a75844b23beaee5c43341e810e299141bff89e00c2b2ef0464` |
| DrakesWorkshop-0.3.0.0-Full-Setup.exe | 114.5 MB | `ffc9e07cd124b644f4b410f36ea2876f649fae9acb76a3c9c91ce1ea7ab0b5bc` |
| DrakesWorkshop-win-Setup.exe | 89.4 MB | `fb0597f55ad11ffc74eb9302c9d583bff2bd976307e2efdc647dc703507d7236` |

`DrakesWorkshop-0.3.0.0-Full-Setup.msi` is the download-page installer. Slim `DrakesWorkshop-win-Setup.exe` + nupkg is the auto-update channel. Content packs also ship from `drakesworkshop-lib-release` (rolling tag `content-latest`).

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### Versioning (0.3.0.0)
- Core is four-part `0.MINOR.PATCH.REVISION` so friend cuts can increment without burning the patch slot (major stays 0 until post-Kickstarter). Worlds, Systems, and feed packs stay independent 3-part semver.

### Fixed (0.3.0.0)
- **Content install no longer freezes the app.** Skipping a package (or the stall watchdog doing it for you) deleted the in-progress unpack folder on the main thread while the installer was still writing to it, which locked the window: the progress bar sat at 100% and Skip / Continue anyway / Quit all stopped responding. Cleanup now runs in the background and never blocks the UI.
- **Install progress shows it is working.** Unpack and file-copy report stage, files written, and elapsed time instead of a static "please wait", so a large pack that legitimately takes minutes no longer looks hung, and the watchdog stops cancelling healthy installs.
- **Always a way out.** The update overlay has a **Quit** button, and Skip dismisses the lock if the download queue already finished.
- Temp folders left behind by an interrupted or force-quit install are cleaned up on the next launch.

### Install (0.3.0.0)
- **Download what the map needs:** worlds stamp `asset_deps`; Play / Host / Join pull missing **Light** packs before launch. Alpha-only deps stay behind a DWK- upgrade prompt.
- Quiet boot still hydrates **Light essentials** only; Misc -> Check for updates pulls the rest.

### Build
- Friend build **0.3.0.0** â€” first four-part Core cut (continues the 0.2.31 friend-track fixes)

See [CHANGELOG.md](../CHANGELOG.md).
