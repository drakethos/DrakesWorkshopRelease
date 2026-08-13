# Drake's Workshop - public releases

Alpha/beta builds for **Drake's Workshop** (Drakethos Games).

## License

Play in **Light** with **no key**  -  Menu, Editor, and Player boot and you can create/play.

A Hauskode **Alpha** key (`DWK-...`) is **optional**. Unlock it from **Unlock Alpha...** when you want the extra entitlements:

- Extra asset packs
- Realistic terrain
- More characters
- Upcoming hosting features

Recover a lost key: https://api.hauskode.com/recover - Apply for Alpha: https://drakesworkshop.net/play?apply=1

## Status

**Current:** [v0.2.26](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.2.26)  -  Light (no key) + optional Alpha (`DWK-`). Prefer the Velopack Setup.exe; portable zips still attached.


## Creator Lua docs (AI / ChatGPT)

Public markdown only - mirrored on every `publish-release` stage. No game source.

| Use | URL |
|-----|-----|
| AI handoff (raw) | https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md |
| LLM index (raw) | https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt |
| Browse | https://github.com/drakethos/DrakesWorkshopRelease/blob/main/docs/lua-api/README.md |

## Layout

```text
releases/
  latest.json                 <- pointer to current version
  index.json                  <- all published versions
  CHANGELOG.md
  0.1.0a/
    notes.md
    checksums.sha256
    # zips are NOT in git - only on the GitHub Release:
    #   DrakesWorkshop-*-Windows.zip   <- first-time install
    #   DrakesWorkshop-*-Update.zip    <- small overwrite update
```

GitHub Actions (`verify-release-assets.yml`) fails a release if either zip is missing or notes omit the optional `DWK-` Alpha upgrade.

## Install (preferred)

1. Download **DrakesWorkshop-*-Setup.exe** from the [Releases](https://github.com/drakethos/DrakesWorkshopRelease/releases) page.
2. Run the installer (Start Menu + Desktop shortcuts).
3. Launch **Drake's Workshop**  -  play in **Light** (no key).
4. Optional: **Unlock Alpha...** and enter a `DWK-` key for extra packs / Realistic terrain / more characters / upcoming hosting.
5. Lost key? [Recover](https://api.hauskode.com/recover) with your email + 8-character code.

Requires the **.NET 8** runtime (Setup can install it).

## Portable (optional)

1. Download **DrakesWorkshop-*-Windows.zip** from [Releases](https://github.com/drakethos/DrakesWorkshopRelease/releases).
2. Unzip to a folder.
3. Run `DrakesWorkshop.exe` (launcher)  -  Light needs no key.
4. Optional: Unlock Alpha... with a `DWK-` key.

## Updates

**Velopack (Setup installs):** the launcher checks GitHub Releases on every start.

**Portable:**

1. Download **DrakesWorkshop-*-Update.zip** for the new version.
2. Unzip **into the same folder** (overwrite when asked).
3. Leave `DrakesWorkshop.exe`, `DrakesWorkshopApp.exe`, and `data_ModuleGameWorkshop_*` alone.

Updates are small (~8-12 MB); the full zip is mostly the engine + .NET runtime (~80 MB).

## Source

Game source is private. This repo ships **binaries (via Releases)**, release notes/manifests, and **creator Lua markdown docs** - no engine/game source tree.

## Maintainers

| Step | Where |
|------|--------|
| Build zips | Private repo: `tools\package-friend-build.cmd` |
| Stage / publish | Private repo: `tools\publish-release.cmd <ver> [--publish]` |
| Architecture | Private repo: `docs/RELEASING.md` |

