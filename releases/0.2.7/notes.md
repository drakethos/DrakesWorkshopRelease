# Drake's Workshop 0.2.7

Released: 2026-07-22T16:50:03Z

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
1. Download **DrakesWorkshop-0.2.7-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) and enter your DWK- key in Editor/Player

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.7-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 90.5 MB | `2f0828623cf1d6aaf92eb2c2f3d999efb9378be162d7cb545c2e6a151d998da7` |
| DrakesWorkshop-0.2.7-Windows.zip | 82.1 MB | `61e1bd67af34d4d3693c871f3d776b99ddbd2fd18163ddd530d1e6e120cd8608` |
| DrakesWorkshop-0.2.7-Update.zip | 12.5 MB | `879575b5ba032d6643c2bbf077c05c9c35a0dd2a613da1cbd9d9f01188a34600` |

Velopack feed is hosted on the Takeoff download host; GitHub also carries Setup + portable zips.

## Changes

- Wave A gate: Main Menu Local / Direct Host and Join + world download (see WAVE-A-DOGFOOD.md)
- Version 0.3.0 â€” publish after dogfood checklist is green
- Wave B scaffolding: native Linux dedicated host package (`server/`)

See [CHANGELOG.md](../CHANGELOG.md).
