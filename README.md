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

**Current:** [v0.3.1.0](https://github.com/drakethos/DrakesWorkshopRelease/releases/tag/v0.3.1.0)  -  Light (no key) + optional Alpha (`DWK-`). Download **Full Setup** (content included); auto-updates stay slim.


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
    # zips/installers are NOT in git - only on the GitHub Release:
    #   DrakesWorkshop-*-Full-Setup.msi <- download page (Program Files)
    #   DrakesWorkshop-*-Full-Setup.exe <- per-user Full Setup
    #   DrakesWorkshop-*-Setup.exe      <- slim auto-update
    #   slim *.nupkg / RELEASES / releases.win.json
```

GitHub Actions (`verify-release-assets.yml`) fails a release if Full Setup or the slim Velopack feed is missing, or notes omit the optional `DWK-` Alpha upgrade.

## Install (preferred)

1. Download **DrakesWorkshop-*-Full-Setup.msi** (Program Files) or **Full-Setup.exe** (per-user) from the [Releases](https://github.com/drakethos/DrakesWorkshopRelease/releases) page (or https://drakesworkshop.net/download).
2. Run the installer. This build includes worlds, meshes, music, and skies â€” first launch installs that content, then the game starts.
3. Launch **Drake's Workshop**  -  first run copies bundled content; later Core updates are small.
4. Optional: **Unlock Alpha...** and enter a `DWK-` key for extra packs / Realistic terrain / more characters / upcoming hosting.
5. Lost key? [Recover](https://api.hauskode.com/recover) with your email + 8-character code.

Requires the **.NET 8** runtime (Setup can install it).

## Updates

**Velopack (Setup installs):** the launcher checks GitHub Releases on every start and downloads **slim Core only**. Missing or newer packs come from the content feed â€” not another full installer.

Updates are small (Velopack nupkg is slim Core). The first-install Full Setup is large because it embeds Light essentials.

## Source

Game source is private. This repo ships **binaries (via Releases)**, release notes/manifests, and **creator Lua markdown docs** - no engine/game source tree.

## Maintainers

| Step | Where |
|------|--------|
| Build zips | Private repo: `tools\package-friend-build.cmd` |
| Stage / publish | Private repo: `tools\publish-release.cmd <ver> [--publish]` |
| Architecture | Private repo: `docs/RELEASING.md` |

