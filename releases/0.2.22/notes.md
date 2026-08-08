# Drake's Workshop 0.2.22

Released: 2026-08-08T16:18:36Z

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
1. Download **DrakesWorkshop-0.2.22-Windows.zip**
2. Unzip to a folder
3. Run `DrakesWorkshop.exe` (launcher) and enter your DWK- key in Editor/Player

### Already installed (portable only)
1. Download **DrakesWorkshop-0.2.22-Update.zip**
2. Unzip into the same folder (overwrite)
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-win-Setup.exe | 581 MB | `e704143a4b4632eb5a869612b576aaa8568ed4b92278f2639c1e7a80e27abd8e` |
| DrakesWorkshop-0.2.22-Windows.zip | 572.9 MB | `9890eea53009439ba49733d516a12a5ec2758c0a0b6ca4644217c40bab39000a` |
| DrakesWorkshop-0.2.22-Update.zip | 503.3 MB | `a7971401a46e02fd3153535c8505f248e1396ded70762c970754be47745b10d9` |

Velopack feed is hosted on the Takeoff download host; GitHub also carries Setup + portable zips.

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### New
- **Content feed (GitHub):** Systems + official worlds ship via rolling Release `content-latest` on `DrakesWorkshopRelease` â€” update without a new Core Setup (`tools\publish-content.cmd --deploy`)
- Main Menu / Editor quiet content check (`ContentClient`) installs to `user://modules` + official worlds
- World `manifest.version` + System pack semver / `minCore` gates; `modules/systems-release.json` + `SYSTEMS.md` catalog thread

### Fixes
- Soft status when content feed is not published / unreachable (local packs remain)
- Content publish uses `gh` (no Takeoff/SSH required for content)

### Build
- Friend build **0.2.22** â€” GitHub content feed client + gates
- Content channel: rolling **`content-latest`** (pack versions stay per-System / per-world; this Core is on the **0.2** friend track)
- Wave A / **0.3.0** still waits on Direct Connect dogfood

See [CHANGELOG.md](../CHANGELOG.md).
