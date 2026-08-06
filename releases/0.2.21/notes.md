# Drake's Workshop 0.2.21

Released: 2026-08-06T02:00:28Z

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
1. Download **DrakesWorkshop-0.2.21-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) and enter your DWK- key in Editor/Player

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.21-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 124.9 MB | `f11e25a05dbaf474a961110b154868211336b5a42628a70eccb6f3e38f3797d3` |
| DrakesWorkshop-0.2.21-Windows.zip | 116.5 MB | `c350405a607deea2ef18eadca8f3573750bbdd0dd83a364248ec7cba4c98fb80` |
| DrakesWorkshop-0.2.21-Update.zip | 46.9 MB | `950756613248e71e7294c2988a4b9f1b3b66e7a2c96f8ed1cf2b885d042a69c7` |

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
- **0.2.20:** **The Floor Is Lava** official world; lava / water surface shaders + `lava` / `water` / `hazard_fluid` Lua APIs; light markers; editor inspector / layout / model-preview polish

### Fixes
- Lobby / load-screen sync and seat UX polish
- World package IO, region markers, and player launch intent edge cases
- Editor stability and inspector layout issues
- Don't Drown / RCS gameplay + systems tweaks (health, inventory, player management)
- Brand chrome + nametag consistency across menu / player
- **0.2.17:** networked humans register into match racers (robot look + drown) â€” stop EntitySync ghosts outside Lua rules; skip menu-skin overwrite in predefined matches
- **0.2.18:** late joiners teleport to race spawn with the robots; tone down morning fog wash / cap camera zoom (peach void speck)
- **0.2.19:** map ENet peers to compact Player1..Player8 slots (fixes RCS lobby spawn at Xâ‰ˆbillions / Player1399â€¦)
- **0.2.20:** terrain / water material + pack catalog edge cases; WorldPackage light-marker + fluid system wiring

### Build
- Friend build **0.2.20** (Wave A / 0.3.0 still waiting on Direct Connect dogfood)

See [CHANGELOG.md](../CHANGELOG.md).
