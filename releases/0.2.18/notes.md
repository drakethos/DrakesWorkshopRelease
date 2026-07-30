# Drake's Workshop 0.2.18

Released: 2026-07-30T03:44:51Z

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
1. Download **DrakesWorkshop-0.2.18-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) and enter your DWK- key in Editor/Player

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.18-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 116 MB | `0f6c5b09de026d6fffe07fa97453ba7b731510a9a1fee82a3fb2478144507db0` |
| DrakesWorkshop-0.2.18-Windows.zip | 107.6 MB | `03e07cb8319e38462ff5b4267e4bed8df7ee049e5e12d45ae1331ac93420a7e8` |
| DrakesWorkshop-0.2.18-Update.zip | 38 MB | `62544e2a112d2de21cc8c6fb796d5d6504d6016efedbf2a62cae7f164aa1b94e` |

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
- **0.2.17:** networked humans register into match racers (robot look + drown) â€” stop EntitySync ghosts outside Lua rules; skip menu-skin overwrite in predefined matches
- **0.2.18:** late joiners teleport to race spawn with the robots; tone down morning fog wash / cap camera zoom (peach void speck)

### Build
- Friend build **0.2.18** (Wave A / 0.3.0 still waiting on Direct Connect dogfood)

See [CHANGELOG.md](../CHANGELOG.md).
