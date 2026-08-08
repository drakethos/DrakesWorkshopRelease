# Drake's Workshop 0.2.23

Released: 2026-08-08T21:04:59Z

## License (required)

This build is **license-gated**. You need a beta access key starting with **DWK-**.
Recover: https://api.hauskode.com/recover

## Install (preferred)

1. Download **DrakesWorkshop-win-Setup.exe** from the [GitHub Release](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.2.23)
2. Run the installer (Start Menu + Desktop shortcuts)
3. Launch Drakes Workshop -- launcher checks **GitHub Releases** for updates on every start
4. Enter your DWK- key when Editor/Player prompts

Requires the **.NET 8** runtime (Setup can install it).

Auto-update: Velopack GithubSource â†’ `https://github.com/drakethos/DrakesWorkshopRelease` (nupkg + RELEASES on this tag).

## Portable (optional)

### First time
1. Download **DrakesWorkshop-0.2.23-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) and enter your DWK- key in Editor/Player

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.23-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 581 MB | `a410e34c0f943db478998a757cdfea7c9df64c9ad301485ded9d4439c6385bd3` |
| DrakesWorkshop-0.2.23-Windows.zip | 572.9 MB | `295d5655ef2cfde4d9ccc2a2c991cef7ac899722d13529be449ca997d369b318` |
| DrakesWorkshop-0.2.23-Update.zip | 503.3 MB | `32c0340db8e950d72ea226245c0ec359962120f2bb2db71c3d01e04058cc9f09` |

Velopack feed (`*.nupkg`, `releases.win.json`) is attached to this GitHub Release. Content packs use the separate `content-latest` rolling tag.

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### New
- Content versions rebased to **0.1.x** (Systems + official worlds) â€” early track, not 1.0
- Official worlds: `sandbox_demo`, `robots_cant_swim`, `the_floor_is_lava` at **0.1.0**

### Fixes
- Default new-world `manifest.version` is now **0.1.0** (was 1.0.0)

### Build
- Friend build **0.2.23** â€” Core patch on the **0.2** friend track
- Systems catalog (rebased): core **0.1.3**, platform/sandbox **0.1.4**, adventure **0.1.2**, rpg/rts **0.1.0**
- Wave A / **0.3.0** still waits on Direct Connect dogfood

See [CHANGELOG.md](../CHANGELOG.md).
