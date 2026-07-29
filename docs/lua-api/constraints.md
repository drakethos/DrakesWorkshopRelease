# Creator Lua constraints

Rules for world scripts, shipped libs/systems, and AI assistants.

## Architecture

- Drake's Workshop is an **empty shell**: the host is C#; **Lua drives gameplay**.
- Prefer **libs** and **systems** over inventing new host APIs. Never invent C# for a world.
- There is **no** Roblox-style `Player` / `Entity` / `World` OOP. Use flat globals and namespaced libs.

## Identity and entities

- Local player entity id: `GetLocalPlayer()` (string).
- Display name: `GetLocalDisplayName()` (Main Menu character name).
- Check existence with `HasEntity(id)` before moving or damaging.

## Includes and placement

- Preloaded libs (always on): `basic`, `animation`, `audio`, `sandbox`, `platform`, `game`, `condition`.
- Include-only: `match_ui`, `match_end`, `input` → `Include("match_ui.lua")` (etc.).
- Map override: `scripts/lib/<name>.lua` wins over shipped libs. Do not edit shipped core libs for one map.
- Reusable logic → lib or system. Map-only logic → `scripts/<name>.lua`.

## Systems

- Enable packs in the Editor **Systems** tab or `systems.json`.
- While a pack loads, `SystemConfig` holds its Inspector params.
- Public functions from a system exist only when that pack is enabled.
- `player_control` owns WASD + Space jump. Custom jump (double/triple) must **cooperate** — e.g. mid-air `CharacterMove(id, 0, 0, jumpY)` after the first floor jump — not blindly rebind Space on top of the pack.

## Style

- Prefer `Game.Message(...)` over raw `DisplayGameMessage`.
- Prefer `Basic.*` / `Audio.*` / `Animation.*` wrappers when they fit.
- Document public lib/system functions with `---@category` / `---@label` / `---@summary` / `---@snippet` for the Script Lib picker and docs export.
