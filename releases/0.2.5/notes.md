# Drake's Workshop 0.2.5

Released: 2026-07-22T14:14:44Z

## License (required)

This build is **license-gated**. You need a beta access key starting with **DWK-**.
Recover: https://api.hauskode.com/recover

## Install (preferred)

1. Download **DrakesWorkshop-win-Setup.exe** (GitHub Release or https://api.hauskode.com/downloads/drakes-workshop/)
2. Run the installer (Start Menu + Desktop shortcuts)
3. Launch Drakes Workshop -- launcher checks Takeoff downloads for the newest build on every start
4. Enter your DWK- key when Editor/Player prompts

Requires the **.NET 8** runtime (Setup can install it).

Auto-update feed: `https://api.hauskode.com/downloads/drakes-workshop/`
## Portable (optional)

### First time
1. Download **DrakesWorkshop-0.2.5-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) and enter your DWK- key in Editor/Player

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.5-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 90.4 MB | `e6bd7591fb4e687b99459a6470b696317118ebc19214bac0f0d4393dd7a0fe24` |
| DrakesWorkshop-0.2.5-Windows.zip | 82.1 MB | `a4fcc93a521446a0718322991791370fbf7c82ffe42d93f1346275e04d6540ac` |
| DrakesWorkshop-0.2.5-Update.zip | 12.5 MB | `ea34932fe93ab79f9aee4c8267d8160c64630aa05797821af3e01cd839f38cb0` |

Velopack feed is hosted on the Takeoff download host; GitHub also carries Setup + portable zips.

## Changes

- Wave A gate: Main Menu Local / Direct Host and Join + world download (see WAVE-A-DOGFOOD.md)
- Version 0.3.0 â€” publish after dogfood checklist is green
- Wave B scaffolding: native Linux dedicated host package (`server/`)

See [CHANGELOG.md](../CHANGELOG.md).
