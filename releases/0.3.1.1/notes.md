# Drake's Workshop 0.3.1.1

Released: 2026-08-23T03:51:12Z

## License (Alpha optional)

Play in **Light** with no key. A **DWK-** key upgrades to **Alpha** (extra packs, Realistic terrain, more characters, upcoming hosting).
Recover: https://api.hauskode.com/recover - Apply: https://drakesworkshop.net/play?apply=1

## Install (preferred)

1. Download **DrakesWorkshop-0.3.1.1-Full-Setup.msi** from the [GitHub Release](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.3.1.1) or https://drakesworkshop.net/download
2. **DrakesWorkshop-0.3.1.1-Full-Setup.msi** installs to Program Files (admin). The .exe is a per-user LocalAppData install.
3. Setup installs Core **and content** (meshes, music, skies, worlds). First launch finishes extracting bundled packs, then the game starts.
4. Play in Light. Optional: Unlock Alpha... and enter your DWK- key

Requires the **.NET 8** runtime (Setup can install it).

## Updates

Quit and relaunch. Auto-update downloads **slim Core only** (`DrakesWorkshop-win-Setup.exe` / nupkg) -- not another full content installer. Missing or newer packs come from the content feed.

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-0.3.1.1-Full-Setup.msi | 99.4 MB | `7d041105c830545fddbdb447b2b556948bde02f4e5ea2fdc415af48c7b1a94f4` |
| DrakesWorkshop-0.3.1.1-Full-Setup.exe | 114.5 MB | `7ced87dd7dbb57d770273a0d87b79e737c837c09fa30139ba681e658aa2212fc` |
| DrakesWorkshop-win-Setup.exe | 89.5 MB | `94db8eb36f471015bf5d794215ced096852d9813298e1f2ebad574ddaea01d7d` |

`DrakesWorkshop-0.3.1.1-Full-Setup.msi` is the download-page installer. Slim `DrakesWorkshop-win-Setup.exe` + nupkg is the auto-update channel. Content packs also ship from `drakesworkshop-lib-release` (rolling tag `content-latest`).

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### Versioning (0.3.1.1)
- Core revision on the 0.3.1 track (Velopack feed `0.3.101`).

### Fix (0.3.1.1)
- Friend installs no longer treat System **seed JSON** as enough for gameplay. Full Setup / content hydrate now require System Lua under `user://modules`, and the content feed will install `sys-*` packs when they are missing.
- Symptom this fixes: official maps load geometry but never spawn characters / run world scripts (e.g. Robots Can't Swim).

### Build
- Friend build **0.3.1.1** â€” System Lua hydrate gate + pack layout aliases from 0.3.1.0

See [CHANGELOG.md](../CHANGELOG.md).
