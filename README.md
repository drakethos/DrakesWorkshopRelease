# Drake's Workshop - public releases

Alpha/beta builds for **Drake's Workshop** (Drakethos Games). Downloads are **license-gated**: you need a beta access key (`DWK-...`) from us to run the app.

## Status

**Current:** [v0.2.22](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.2.22) - license-gated beta (`DWK-` keys). Prefer the Velopack Setup.exe; portable zips still attached.

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
    #   DrakesWorkshop-0.1.0a-Windows.zip   <- first-time install
    #   DrakesWorkshop-0.1.0a-Update.zip    <- small overwrite update
```

GitHub Actions (`verify-release-assets.yml`) fails a release if either zip is missing or notes omit the `DWK-` license requirement.

## Install

1. Download **DrakesWorkshop-*-Windows.zip** from the [Releases](https://github.com/drakethos/DrakesWorkshopRelease/releases) page.
2. Unzip to a folder.
3. Run `DrakesWorkshop.exe`.
4. Enter your **DWK-** beta key when prompted.
5. Lost key? [Recover](https://api.hauskode.com/recover) with your email + 8-character code.

## Updates

If you already have an install:

1. Download **DrakesWorkshop-*-Update.zip** for the new version.
2. Unzip **into the same folder** (overwrite when asked).
3. Leave `DrakesWorkshop.exe` and the rest of `data_ModuleGameWorkshop_*` alone.

Updates are small (~8 MB); the full zip is mostly the engine + .NET runtime (~80 MB).

## Source

Game source is private. This repo ships **binaries (via Releases)**, release notes/manifests, and **creator Lua markdown docs** - no engine/game source tree.
## Maintainers

| Step | Where |
|------|--------|
| Build zips | Private repo: `tools\package-friend-build.cmd` |
| Stage / publish | Private repo: `tools\publish-release.cmd 0.1.0a [--publish]` |
| Architecture | Private repo: `docs/RELEASING.md` |


