# Drake's Workshop 0.3.1.0

Released: 2026-08-19T19:00:27Z

## License (Alpha optional)

Play in **Light** with no key. A **DWK-** key upgrades to **Alpha** (extra packs, Realistic terrain, more characters, upcoming hosting).
Recover: https://api.hauskode.com/recover - Apply: https://drakesworkshop.net/play?apply=1

## Install (preferred)

1. Download **DrakesWorkshop-0.3.1.0-Full-Setup.msi** from the [GitHub Release](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.3.1.0) or https://drakesworkshop.net/download
2. **DrakesWorkshop-0.3.1.0-Full-Setup.msi** installs to Program Files (admin). The .exe is a per-user LocalAppData install.
3. Setup installs Core **and content** (meshes, music, skies, worlds). First launch finishes extracting bundled packs, then the game starts.
4. Play in Light. Optional: Unlock Alpha... and enter your DWK- key

Requires the **.NET 8** runtime (Setup can install it).

## Updates

Quit and relaunch. Auto-update downloads **slim Core only** (`DrakesWorkshop-win-Setup.exe` / nupkg) -- not another full content installer. Missing or newer packs come from the content feed.

## Files

| File | Size | SHA-256 |
|------|------|---------|
| DrakesWorkshop-0.3.1.0-Full-Setup.msi | 99.3 MB | `e33d32d785c304839355c63d39eb3170a865512bb52e623e9f1ee512a0fb95d1` |
| DrakesWorkshop-0.3.1.0-Full-Setup.exe | 114.5 MB | `b040fb7dfdb226cc30e99086b521a31b27f9bddbbf4b15c0dcb57753a7c947c1` |
| DrakesWorkshop-win-Setup.exe | 89.5 MB | `3b02ac1dcf19e2ca7edd6cafbb103dd0cde868e8c20906b9a8ef0e02a1df0c35` |

`DrakesWorkshop-0.3.1.0-Full-Setup.msi` is the download-page installer. Slim `DrakesWorkshop-win-Setup.exe` + nupkg is the auto-update channel. Content packs also ship from `drakesworkshop-lib-release` (rolling tag `content-latest`).

## Creator Lua docs (AI / ChatGPT)

Public markdown only (no game source):

- AI handoff: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- LLM index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt
- Browse: https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md

## Changes

### Versioning (0.3.1.0)
- Core patch on the 0.3 track (Velopack feed `0.3.100`). Mesh packs on the content feed move to stable **1.0.0** (Kenney + Quaternius). Date-stamp installs still update once onto 1.0.0.

### Editor (0.3.1.0)
- Place palette no longer restores Tree selection after a rebuild (Godot 4.7 fatal inside `TreeItem.Select` / `Clear`).
- Pack and object place trees always have one column before fill.
- `tools/launch-godot.cmd` builds C# before launching the player so stale Debug DLLs are not reused.

### Content (0.3.1.0)
- Remaining Quaternius kits ship on the Alpha content feed (not Full Setup). Light still skips them until a DWK- key.
- Interactive Check for updates pulls the new packs; quiet boot still hydrates Light essentials only.

### Build
- Friend build **0.3.1.0** â€” editor stability + Quaternius content feed

See [CHANGELOG.md](../CHANGELOG.md).
