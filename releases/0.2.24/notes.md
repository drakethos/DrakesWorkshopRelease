# Drake's Workshop 0.2.24

Released: 2026-08-11T13:28:01Z

## License (required)

This build is **license-gated**. You need a beta access key starting with **DWK-**.
Recover: https://api.hauskode.com/recover

## Install (preferred)

1. Download **DrakesWorkshop-win-Setup.exe** from the [GitHub Release](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.2.24)
2. Run the installer (Start Menu + Desktop shortcuts)
3. Launch Drakes Workshop -- launcher checks **GitHub Releases** for updates on every start
4. Enter your DWK- key when Editor/Player prompts

Requires the **.NET 8** runtime (Setup can install it).

Auto-update: Velopack GithubSource â†’ `https://github.com/drakethos/DrakesWorkshopRelease` (nupkg + RELEASES on this tag).

## Portable (optional)

### First time
1. Download **DrakesWorkshop-0.2.24-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) and enter your DWK- key in Editor/Player

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.24-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 88.7 MB | `7f3a6669893b4c36d511b36f8fa1631dd571af8b704413b59c833b0aef1452b0` |
| DrakesWorkshop-0.2.24-Windows.zip | 80.4 MB | `10449b9dd075a5ca0eda1ab049a153fb3602127eb0ce41d2cd42e0397bcf3beb` |
| DrakesWorkshop-0.2.24-Update.zip | 10.8 MB | `ea8fcd5fabcc04a5cc732a3bcc0e95dd3fa3349f4d30ab880a738bd86767fc49` |

Velopack feed (`*.nupkg`, `releases.win.json`) is attached to this GitHub Release. Content packs use the separate `content-latest` rolling tag.

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### New
- Slim Core friend cut: Lua + pack/env/audio assets ship via the content feed (not inside Setup)
- Content versions on **0.1.x** (Systems + official worlds)

### Fixes
- Default new-world `manifest.version` is **0.1.0** (was 1.0.0)

### Build
- Friend build **0.2.24** â€” Core patch on the **0.2** friend track
- Systems catalog: core **0.1.3**, platform/sandbox **0.1.4**, adventure **0.1.2**, rpg/rts **0.1.0**
- Wave A / **0.3.0** still waits on Direct Connect dogfood

See [CHANGELOG.md](../CHANGELOG.md).
