# Drake's Workshop 0.2.13

Released: 2026-07-28T04:46:31Z

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
1. Download **DrakesWorkshop-0.2.13-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) and enter your DWK- key in Editor/Player

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.13-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 113.7 MB | `163c305baf36bdba65cd7182634cc633f505b9aeaa5bdecc7db5b93fedde0058` |
| DrakesWorkshop-0.2.13-Windows.zip | 105.3 MB | `15cd06bb75a626137f4506e88a195da75ddbbd89ec0844d03fb843142d01711b` |
| DrakesWorkshop-0.2.13-Update.zip | 35.7 MB | `9396eea3140f2ffa51180fe0c7fd9218949f301222588b31df82f0b553398b6c` |

Velopack feed is hosted on the Takeoff download host; GitHub also carries Setup + portable zips.

## Changes

- Genre Systems: Core hosts resources, ambient music, scoreboard, teams
- Resources HUD pin (`free` / `ui_bar` / `inventory`); Adventure pins near inventory, RTS to UI bar
- RTS genre pack + Selection settings stub; genre loadouts (RTS disables Player/Health)
- Friend build 0.2.13 (Wave A / 0.3.0 still waiting on Direct Connect dogfood)

See [CHANGELOG.md](../CHANGELOG.md).
