# Drake's Workshop 0.2.12

Released: 2026-07-27T23:13:08Z

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
1. Download **DrakesWorkshop-0.2.12-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) and enter your DWK- key in Editor/Player

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.12-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 113 MB | `9e19d3c65e88451d64c5753996f81e0e112fe57c1717bf28c900b7a4942def17` |
| DrakesWorkshop-0.2.12-Windows.zip | 104.6 MB | `6d32d6696b10a7e71132f586db7c51086e31495859ca725887a0b4ecdaed5f90` |
| DrakesWorkshop-0.2.12-Update.zip | 35 MB | `00f9523156d98a607717acbb3a7396c3b2c5c3fac813e69f48e5fc23dc08bb15` |

Velopack feed is hosted on the Takeoff download host; GitHub also carries Setup + portable zips.

## Changes

- Object editor panel + ObjectCatalog (sandbox object schema / sample objects)
- New map wizard, sky HDR environments, main menu ambient polish
- Editor game/inspector/world fixes; pack layout cleanup (castle / platformer / nature)
- Lua: template folders, clock + time_scale systems
- Kenney pack expansion (audio, placeables, mini chars, cursors); texture atlas fixes; weapon grip / music polish
- Friend build 0.2.12 (Wave A / 0.3.0 still waiting on Direct Connect dogfood)

See [CHANGELOG.md](../CHANGELOG.md).
