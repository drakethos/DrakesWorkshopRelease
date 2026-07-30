# Drake's Workshop 0.2.16

Released: 2026-07-30T00:35:14Z

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
1. Download **DrakesWorkshop-0.2.16-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) and enter your DWK- key in Editor/Player

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.16-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 113.7 MB | `62eccc53d34b1f01be4e68eede26522edd225af71c4dae5852c0e42fc7bd1165` |
| DrakesWorkshop-0.2.16-Windows.zip | 105.3 MB | `d18977b7faf1fc7aca2e0038844b532ba21372a1c24b779dffef573b008effc5` |
| DrakesWorkshop-0.2.16-Update.zip | 35.7 MB | `bcd920ead7bcd05836d3ad83455b1028e599d12ba93d48ac1b61c099d3a1d7db` |

Velopack feed is hosted on the Takeoff download host; GitHub also carries Setup + portable zips.

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### New
- **Robots Can't Swim** official world â€” lobby race, robot swim/drown rules, match music
- Match chrome: scoreboard, countdown (READY/3/2/1), intro overlay, game message toasts
- Match end dialog + host remake invite (main-menu rejoin path)
- In-app **Settings** (audio / window) from main menu and pause
- Creator **FX** host API + fire / smoke / sparks prop templates
- Public **Lua API docs** pipeline (`docs/lua-api/`, AI-CONTEXT / llms.txt sync on publish)
- Editor **Player Setup** improvements; inspector / terrain polish
- Quick play / edit helper cmds for official worlds

### Fixes
- Lobby / load-screen sync and seat UX polish
- World package IO, region markers, and player launch intent edge cases
- Editor stability and inspector layout issues
- Don't Drown / RCS gameplay + systems tweaks (health, inventory, player management)
- Brand chrome + nametag consistency across menu / player

### Build
- Friend build **0.2.16** (Wave A / 0.3.0 still waiting on Direct Connect dogfood)

See [CHANGELOG.md](../CHANGELOG.md).
