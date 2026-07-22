# Drake's Workshop 0.2.4

Released: 2026-07-22T02:59:05Z

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
1. Download **DrakesWorkshop-0.2.4-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) and enter your DWK- key in Editor/Player

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.4-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 99.5 MB | `10fdfe159d95bdb95d9b3c731d825ad1534aa85ea4c1414cf66384d44898ed5f` |
| DrakesWorkshop-0.2.4-Windows.zip | 91.1 MB | `436917edc7a3063c13ff3823d5314e77f4f3d297a35a9ba06e2b481f66784481` |
| DrakesWorkshop-0.2.4-Update.zip | 21.5 MB | `35f9d34d06d3d22b5b007ee18af2244055189cbfcd619f489857cedb2c79b1d7` |

Velopack feed is hosted on the Takeoff download host; GitHub also carries Setup + portable zips.

## Changes

- Main Menu Multiplayer: Local / Direct Host and Join (Online stub for Wave B)
- Peer host world download for joiners before load
- N-peer pose sync (`Player{N}`); soft-cap 8 on UDP 7777
- Velopack **Setup.exe** attached on the GitHub Release (preferred install)

See [CHANGELOG.md](../CHANGELOG.md).
