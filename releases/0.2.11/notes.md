# Drake's Workshop 0.2.11

Released: 2026-07-25T03:38:09Z

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
1. Download **DrakesWorkshop-0.2.11-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) and enter your DWK- key in Editor/Player

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.11-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 98.4 MB | `1e423e7934435eaf5f4c8d727b2ff2c9981565d0f87977c11caae97608738cba` |
| DrakesWorkshop-0.2.11-Windows.zip | 90 MB | `af4c510d80df01a56970617c1c03932a23054e4b778eaab35e67fc45f29ab267` |
| DrakesWorkshop-0.2.11-Update.zip | 20.4 MB | `68c96245a9df9c871fbb16e9d7b9198e86dcffdaef4394b35584d76a6585ee0b` |

Velopack feed is hosted on the Takeoff download host; GitHub also carries Setup + portable zips.

## Changes

- Object editor panel + ObjectCatalog (sandbox object schema / sample objects)
- New map wizard, sky HDR environments, main menu ambient polish
- Editor game/inspector/world fixes; pack layout cleanup (castle / platformer / nature)
- Lua: template folders, clock + time_scale systems
- Friend build 0.2.11 (Wave A / 0.3.0 still waiting on Direct Connect dogfood)

See [CHANGELOG.md](../CHANGELOG.md).
