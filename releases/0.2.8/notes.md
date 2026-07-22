# Drake's Workshop 0.2.8

Released: 2026-07-22T22:09:54Z

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
1. Download **DrakesWorkshop-0.2.8-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) and enter your DWK- key in Editor/Player

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.8-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 90.8 MB | `a555d187ac03ca1d043264e50de3e06345064a85a7b101edc95dc7ed322d5b76` |
| DrakesWorkshop-0.2.8-Windows.zip | 82.5 MB | `cea468398bb1a18ac0e9a2b3b461f10490cef0af08de435c3809e629ffbd15d5` |
| DrakesWorkshop-0.2.8-Update.zip | 12.9 MB | `0825ebdc86efaa1b72dc5d186ebeac3bf79d07ca753049c90a7d153b3e18f2e6` |

Velopack feed is hosted on the Takeoff download host; GitHub also carries Setup + portable zips.

## Changes

- Terrain paint palette: per-tile Grass / Dirt / Stone colors + swatches (repaint without global Floor tint)
- Kid-friendly terrain brush pictures (grass, dirt, stone, snow, water)
- ship_cruise.lua: stay on water â€” no more sky-climbing when dry; pirate ship models in pack
- Friend build 0.2.8 (Wave A / 0.3.0 still waiting on dogfood checklist)

See [CHANGELOG.md](../CHANGELOG.md).
