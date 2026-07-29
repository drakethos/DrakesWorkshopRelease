# Drake's Workshop — Lua API

Creator-facing **runtime Lua** reference: helper libraries, systems packs, and the host whitelist globals. Product gameplay stays in Lua; C# is the editor/runtime host only.

| Surface | Path | Use |
|---------|------|-----|
| Libraries | [libs/](libs/) | Prewritten helpers (`Game`, `Basic`, `MatchUi`, …) |
| Systems | [systems/](systems/) | World-wide packs (health, inventory, player_control, …) |
| Host API | [host-api.md](host-api.md) | MoonSharp whitelist always available in scripts |
| Constraints | [constraints.md](constraints.md) | Rules for humans and AIs |
| AI handoff | [AI-CONTEXT.md](AI-CONTEXT.md) | One-file paste/URL pack for ChatGPT / Claude / Cursor |
| Example | [examples/triple-jump-pete.md](examples/triple-jump-pete.md) | Worked multi-jump script |

## Layers

| Layer | Where | Role |
|-------|-------|------|
| **System** | `shared/lua/systems/` | Configurable world behavior (Systems tab / `systems.json`) |
| **Library** | `shared/lua/libs/` | Helpers; most preloaded, some via `Include("name.lua")` |
| **World script** | `user://worlds/*/scripts/` | Map-unique logic + thin `main.lua` |

## Boot order

1. Bind host whitelist  
2. Preload libs: `basic` → `animation` → `audio` → `sandbox` → `platform` → `game` → `condition`  
3. Apply enabled systems (`SystemConfig` per pack)  
4. Run `scripts/main.lua`  
5. Entity-attached scripts  
6. Fire `OnInit`

## Regenerating docs

```bat
powershell -NoProfile -File tools\export-lua-api.ps1
powershell -NoProfile -File tools\export-lua-api.ps1 -Check
```

`-Check` is a `/release` quality gate: fails if generated sections are stale vs source.

## Quick AI prompt

Point ChatGPT at the **public** handoff (or paste the private mirror):

- https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/docs/lua-api/AI-CONTEXT.md
- Index: https://raw.githubusercontent.com/drakethos/DrakesWorkshopRelease/main/llms.txt

Local: [AI-CONTEXT.md](AI-CONTEXT.md) · root [`llms.txt`](../../llms.txt). Then:

> Help me write Lua so a player named Pete can triple-jump.
