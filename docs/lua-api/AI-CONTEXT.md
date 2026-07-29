# Drake's Workshop - AI context pack

Paste this file into ChatGPT / Claude / Cursor (or fetch via `llms.txt`) before asking for world Lua.

**Product:** Drake's Workshop is an empty shell. C# is the editor/runtime host; **Lua drives gameplay**. Prefer shipped libs and systems; never invent C# or Roblox-style `Player`/`Entity` OOP.

## Hard constraints

- Flat host globals + namespaced libs (`Game.Message`, `Basic.Jump`). Entity ids are **strings** from `GetLocalPlayer()`.
- Display name = `GetLocalDisplayName()` (Main Menu character), not a `.Name` property.
- Prefer `Include("name.lua")` for non-preloaded libs (`match_ui`, `match_end`, `input`). Preloaded: basic, animation, audio, sandbox, platform, game, condition.
- Systems are enabled in the Editor Systems tab / `systems.json`. Their public functions appear only when that pack is on.
- World-unique logic belongs in map `scripts/`. Reusable helpers go in a lib or system.
- `player_control` already binds WASD + Space jump. Multi-jump / custom move must cooperate (mid-air `CharacterMove(id, 0, 0, jumpY)`, or disable/override carefully) - do not blindly rebind Space.
- Output: reply with **Lua only** for the requested script path unless asked for explanation.

## Boot order

1. Bind host whitelist
2. Preload helper libs
3. Apply enabled systems (`SystemConfig` pushed per pack)
4. Run `scripts/main.lua`
5. Entity-attached scripts
6. Fire `OnInit`

<!-- BEGIN GENERATED -->
## Host cheat sheet

**Animation:** `ListEntityAnims` - Animation clip names on a model. | `PlayEntityAnim` - Play a clip by name. | `StopEntityAnim` - Stop playing animation.

**Audio:** `ListMusic` - Available music ids (built-in + world). | `ListSounds` - Available SFX ids (built-in + world). | `PlayMusic` - Play music by id (loops by default). | `PlaySound` - Play a one-shot SFX by id. | `StopMusic` - Stop the music channel. | `StopSound` - Stop a sound handle from PlaySound.

**Boot:** `ApplySystem` - Apply a systems pack by id (advanced; prefer Systems tab). | `Include` - Load a Lua lib/template/world script by name (deduped). | `Log` - Print a debug line to the game log.

**Camera:** `GetCameraMovementRelative` - Whether movement is camera-relative. | `GetCameraMoveYaw` - Current camera move yaw degrees. | `SetCameraFollow` - Follow an entity with the camera. | `SetCameraFollowFov` - Camera follow FOV. | `SetCameraFollowOffset` - Camera follow offset x,y,z. | `SetCameraFollowPlayerAdjust` - Enable player orbit/zoom adjust flags. | `SetCameraMovementRelative` - Move relative to camera yaw.

**Clock:** `GetClockHour` - Current in-world clock hour. | `GetClockNormalized` - Clock progress 0-1 through the day. | `GetClockSecondsPerHour` - Real seconds per in-world hour. | `GetClockTimeScale` - Clock time scale multiplier. | `GetWorldSky` - Current sky preset id. | `GetWorldTimeOfDay` - World time-of-day value. | `IsClockRunning` - True if the clock is advancing. | `SetClockHour` - Set in-world clock hour. | `SetClockRunning` - Start or pause the clock. | `SetClockSecondsPerHour` - Set real seconds per in-world hour. | `SetClockTimeScale` - Set clock time scale multiplier.

**Combat:** `AttachEquippedVisual` - Attach equipped tool visual to a player. | `RaycastAimEntity` - Raycast from aim; return entity id within range.

**Entity:** `CharacterMove` - Character controller move: hx, hz horizontal, jumpY impulse. | `DeleteEntity` - Remove an entity. | `GetEntityMaterialStyle` - Get material style id. | `GetEntityMeta` - Read a string meta key. | `GetEntityPackItem` - Pack item id for this entity, if any. | `GetEntityPhysics` - Get physics mode string. | `GetEntityPos` - Return x, y, z position. | `GetEntityRot` - Return euler rotation degrees X,Y,Z. | `GetEntityScale` - Return scale x,y,z. | `GetEntitySizeFactor` - Relative character height factor (grow / scale). | `HasEntity` - True if an entity id exists. | `IsOnFloor` - True when the character is on the floor. | `JumpAll` - Apply jump impulse to all characters. | `ListEntities` - Return all entity ids. | `MoveEntity` - Set world position (x, y, z). | `OffsetEntity` - Nudge position; keeps character velocity. | `RenameEntity` - Rename an entity id. | `SetEntityAlbedoTexture` - Set albedo texture path/id. | `SetEntityColor` - Set albedo RGB 0-1. | `SetEntityMaterialStyle` - Set material style id. | `SetEntityMeta` - Write a string meta key. | `SetEntityMetallic` - Set material metallic. | `SetEntityModel` - Swap the visual model / pack mesh. | `SetEntityPhysics` - Set physics mode string. | `SetEntityRot` - Set euler rotation degrees X,Y,Z. | `SetEntityRoughness` - Set material roughness. | `SetEntityScale` - Set scale x,y,z. | `SetEntityTextureScale` - Set albedo texture scale. | `SetEntityVisible` - Show or hide an entity. | `SpawnEntity` - Spawn a named entity at x,y,z. | `SpawnPackEntity` - Spawn a pack item as an entity.

**Input:** `IsKeyDown` - True while a key is held (e.g. "w", "space"). | `IsMouseButtonDown` - True while a mouse button is held ("left"/"right").

**Interact:** `GetInteractAmount` - Interact amount number. | `GetInteractArg` - Interact argument string. | `GetInteractKind` - Interact kind string. | `GetInteractOnce` - True if interact is one-shot. | `IsInteractable` - True if entity has interact enabled. | `SetInteractable` - Enable/disable interact on an entity.

**Lifecycle:** `OnInit` - Register a callback that runs once after boot. | `OnKey` - Register a key-press callback: OnKey("space", fn). | `OnRegionEnter` - Fire when a character enters a region box: fn(regionId, entityId). | `OnRegionLeave` - Fire when a character leaves a region box: fn(regionId, entityId). | `OnTick` - Register a per-frame callback: fn(dt).

**Lobby:** `GetLobbyOption` - Lobby option by key (max_players, points_to_win, ...). | `GetLobbyPointsToWin` - Points to win from game.json. | `GetLobbyRounds` - Legacy alias for GetLobbyPointsToWin. | `GetMatchLobbySeats` - Match lobby roster after Host Start (or nil). | `GetPlayerSetupOption` - Player-setup option by key. | `GetPlayerSetupSeats` - Player-setup seat rows. | `GetPlayStyle` - "lobby" or "world" from game.json.

**Other:** `ConsumeMatchIntroSkip` | `HideMatchIntro` | `SetMatchIntroText` | `ShowMatchIntro`

**Packs:** `PackExists` - True if a pack id is available.

**Player:** `GetLocalDisplayName` - Active Main Menu character display name. | `GetLocalPlayer` - Entity id string for the local player. | `GetLocalSkin` - Active Main Menu character skin pack id. | `IgnoresSwim` - True if ignore-swim is enabled for this entity. | `IsNetOnline` - True when a network session is active. | `SetIgnoreSwim` - Walk in deep water without swimming (does not float on top).

**Regions:** `IsInRegion` - True when entity center is inside a region prop. | `ListRegions` - Entity ids of all region trigger boxes.

**Scripts:** `AttachEntityScript` - Attach a script file to an entity. | `GetEntityScripts` - Script filenames attached to a prop. | `GetScriptParam` - Read a per-entity script param (Inspector). | `GetScriptParams` - All params for one attached script. | `SetScriptParam` - Write a per-entity script param.

**Spawn:** `GetSpawnPos` - Default spawn position x,y,z. | `GetSpawnPosFor` - Spawn position for a player/entity id.

**Teams:** `GetEntityTeam` - Team number for an entity. | `GetTeamSpawnPos` - Spawn position for a team number. | `SetEntityTeam` - Assign team number.

**Terrain:** `ApplySeedTerrain` - Apply seeded terrain from worldgen options. | `GetTerrainHeightAt` - Terrain height Y at XZ. | `GetWorldHalfExtents` - Playable map half-size X,Z.

**UI:** `ClearMatchScoreboard` - Hide the match scoreboard. | `CloseMenu` - Close the open menu panel. | `DisplayGameMessage` - Show a toast message (prefer Game.Message). | `GetInventorySlots` - Inventory slot layout bridge for HUD. | `SetGameMessageStyle` - Style game messages (anchor, color, duration). | `SetHotbarGrid` - Push hotbar grid + selected slot to HUD. | `SetHudText` - Set simple HUD text string. | `SetInventoryGrid` - Push inventory grid rows to HUD. | `SetMatchScoreboard` - Show top-right match scoreboard table. | `SetResourceHud` - Show resource strip at screen X,Y. | `ShowMatchEndDialog` - Center match-end dialog (win/lose). | `ShowMenu` - Open a simple titled menu panel. | `ShowResourceToast` - Brief resource gain toast.

**Water:** `IsInDeepWater` - True in deep water swim zone (false while ignore-swim). | `IsInShallowWater` - True when wading in shallow water. | `IsInWater` - True when the entity is in water. | `IsOverDeepWater` - True when body is in deep water (ignores SetIgnoreSwim). | `IsWaterAt` - True when XZ is flooded. | `WaterSurfaceY` - Water surface Y at XZ, or nil if dry.

**World:** `SaveWorldNow` - Force-save the current world package.

**Worldgen:** `ClearNeedsWorldgen` - Clear the needs_worldgen flag. | `ClearWorldgenProps` - Remove props spawned by worldgen. | `GetWorldSeed` - Current world seed string. | `JournalTerraform` - Append a terraform journal entry. | `NeedsWorldgen` - True if one-shot worldgen still needed. | `PlaceHeldBlock` - Place the currently held block (key P path). | `SetWorldSeed` - Set world seed string.

## Libs cheat sheet

- `Animation.List` - Return animation clip names on an entity's model (table of strings).
  `local clips = Animation.List(GetLocalPlayer())`
- `Animation.Play` - Play a named animation clip on an entity (from pack AnimationPlayer).
  `Animation.Play(GetLocalPlayer(), "walk")`
- `Animation.Stop` - Stop the current animation on an entity.
  `Animation.Stop(GetLocalPlayer())`
- `Audio.List` - Return available SFX ids (built-in + world audio/).
  `local sounds = Audio.List()`
- `Audio.ListMusic` - Return available music ids (drop tracks into assets/audio/music/ or world audio/).
  `local tracks = Audio.ListMusic()`
- `Audio.Play` - Play a one-shot sound by id or path. Optional volume (0â€“2) and pitch.
  `Audio.Play("click")`
- `Audio.PlayMusic` - Play music by id or path. Loops by default. Empty id = no-op until you drop a track in.
  `Audio.PlayMusic("my_theme")`
- `Audio.Stop` - Stop a one-shot sound by handle from Audio.Play.
  `Audio.Stop(handle)`
- `Audio.StopMusic` - Stop the current music track.
  `Audio.StopMusic()`
- `Basic.Hide` - Hide an entity (still exists in the world).
  `Basic.Hide("door_1")`
- `Basic.Jump` - Impulse-jump the local player if they are on the floor (uses CharacterMove).
  `Basic.Jump()`
- `Basic.Move` - Move an entity to a world position (x, y, z).
  `Basic.Move(GetLocalPlayer(), 0, 1, 0)`
- `Basic.Rotate` - Set entity euler rotation in degrees (matches Editor Rot XYZ).
  `Basic.Rotate(GetLocalPlayer(), 0, 90, 0)`
- `Basic.Scale` - Set entity scale (x, y, z). Minimum axis size is enforced by the host.
  `Basic.Scale("crate_1", 1.5, 1.5, 1.5)`
- `Basic.SetIgnoreSwim` - Walk in deep water without swimming (does not place you on top of water). Flip false to restore swim.
  `SetIgnoreSwim(GetLocalPlayer(), true)`
- `Basic.Show` - Make an entity visible.
  `Basic.Show("door_1")`
- `Condition.Distance` - World-unit distance between two entities (999999 if missing).
  `local d = Condition.Distance(GetLocalPlayer(), "chest")`
- `Condition.Farther` - True if entityA is farther than distance units from entityB.
  `Condition.Farther(GetLocalPlayer(), "chest", 5)`
- `Condition.HasEntity` - True if an entity id exists in the world.
  `Condition.HasEntity("chest")`
- `Condition.IgnoresSwim` - True if the unit ignores swim (walks in deep water without swimming).
  `Condition.IgnoresSwim(GetLocalPlayer())`
- `Condition.InRegion` - True if entity center is inside a region trigger box.
  `Condition.InRegion(GetLocalPlayer(), "finish")`
- `Condition.Within` - True if entityA is within distance units of entityB (e.g. stand near a chest).
  `Condition.Within(GetLocalPlayer(), "chest", 5)`
- `Game.Message` - Show a game message (toast). Audience: all, local, triggering, Player1, Player2.
  `Game.Message("Hello!", "all")`
- `Input.Freeze` - Freeze character move/attack for one entity, a list, or "all". Does not block menu or pause.
  `Input.Freeze("all")`
- `Input.IsFrozen` - True when this entity (or global "all") has character input frozen.
  `if Input.IsFrozen(me) then return end`
- `Input.Unfreeze` - Restore character gameplay input for one entity, a list, or "all".
  `Input.Unfreeze("all")`
- `MatchEnd.Meets` - True when value meets target using op (>, >=, <, <=, ==).
  `MatchEnd.Meets(wins, 3, ">=")`
- `MatchEnd.OnThreshold` - When value meets target, show the match-end dialog once and return true.
  `MatchEnd.OnThreshold(winnerId, wins, points_to_win, ">=", opts)`
- `MatchEnd.Reset` - Allow another match-end dialog in the same session (rematch / dev).
  `MatchEnd.Reset()`
- `MatchEnd.Show` - Show the match-end dialog (win/lose headline + quit; host may get remake).
  `MatchEnd.Show({ winner = id, loser = id2, winner_name = "RED", loser_name = "BLUE" })`
- `MatchUi.Countdown` - Return the next READY/number/GO countdown message when elapsed time reaches it.
  `local message, index, done = MatchUi.Countdown(elapsed, shown, 3, 0.9, 0.8)`
- `MatchUi.IntroHide` - Hide the intro overlay.
  `MatchUi.IntroHide()`
- `MatchUi.IntroSet` - Update intro banner text (keeps dim / skip button).
  `MatchUi.IntroSet("Click to punch!")`
- `MatchUi.IntroShow` - Top-of-screen how-to overlay with screen dim and optional host Skip.
  `MatchUi.IntroShow("HOW TO PLAY", { skip_label = "SKIP INTRO", dim = 0.42 })`
- `MatchUi.IntroSkipped` - True once after the host presses Skip intro (consumes the flag).
  `if MatchUi.IntroSkipped() then begin_countdown() end`
- `MatchUi.Message` - Show a match message through the shared game-message API.
  `MatchUi.Message("GO!", "all")`
- `MatchUi.RobotSlots` - Show fixed robot color slots (filled or empty) before a lobby match starts.
  `MatchUi.RobotSlots("ROBOT SLOTS", slots, "Waiting for start")`
- `MatchUi.Scoreboard` - Render a structured top-right table scoreboard (falls back to HUD text).
  `MatchUi.Scoreboard("RACE", "GO!", rows)`
- `Platform.Bounce` - Launch an entity upward (bounce pad style).
  `Platform.Bounce(GetLocalPlayer(), 8)`
- `Platform.HazardKill` - Simple hazard: respawn the local player when they touch a tagged entity.
  `-- use with OnTick near-check in your script`
- `Sandbox.Attack` - Deal damage to the nearest enemy in front of the local player (left-click combat).
  `Sandbox.Attack()`
- `Sandbox.BreakApart` - Break a marked breakable prop into rigid chunks.
  `Sandbox.BreakApart("crate_1")`
- `Sandbox.Respawn` - Respawn the local player at the spawn point (heals when Health is on).
  `Sandbox.Respawn()`

## Systems cheat sheet

### `ambient_music`
Game Baseline â€” ambient_music.lua Plays a looping music bed on world load when a real music id is set. Jingles live under sfx/ (PlaySound); drop beds into assets/audio/music/.
- **SystemConfig:** enabled, music, volume
- **API:** (config only)

### `building`
Sandbox Ã¢â‚¬â€ building.lua Block place / build tables. Tables edited in the Build Data tab.
- **SystemConfig:** build_tables, enabled, key_place, place_range, require_item, snap_grid
- **API:** IsBuildingEnabled, ListBuildTables, TryPlaceBlock
  - `IsBuildingEnabled()` - True if building pack is enabled.
  - `ListBuildTables()` - List build table ids.
  - `TryPlaceBlock()` - Try placing the held block.

### `camera`
Game Baseline â€” camera.lua (P1-26) Follow local player in Play / Run Lua (mode from SystemConfig). Player can wheel-zoom / RMB-orbit while stay locked on the followed entity unless player_orbit / player_zoom are disabled.
- **SystemConfig:** fov, mode, movement_relative, offset_x, offset_y, offset_z, player_orbit, player_zoom
- **API:** (config only)

### `chat`
Core Ã¢â‚¬â€ chat.lua (stub) Team / global / positional text chat. Networking + UI land later.
- **SystemConfig:** enabled, key_chat, lock_team, max_distance, mode
- **API:** IsChatEnabled, GetChatMode, GetChatMaxDistance, SendChatMessage
  - `IsChatEnabled()` - True if chat is enabled.
  - `GetChatMode()` - Chat mode string.
  - `GetChatMaxDistance()` - Proximity chat max distance.
  - `SendChatMessage(text, channel)` - Send a chat message (stub).

### `clock`
Game Baseline â€” clock.lua In-world hour clock. Starts from world.env.time_of_day (night default) unless start_hour is set. Sky visuals stay on the world sky preset for now; scripts can read/set the clock.
- **SystemConfig:** seconds_per_hour, start_hour
- **API:** (config only)

### `combat`
Game Baseline Ã¢â‚¬â€ combat.lua Left-click melee when a tool (sword) is equipped. Damages nearest enemy.lua target.
- **SystemConfig:** cooldown, damage, enemy_max_hp, range, require_tool, starter_sword
- **API:** IsEnemyAlive, DamageEnemy, AttackAimTarget
  - `IsEnemyAlive(id)` - True if enemy entity is alive.
  - `DamageEnemy(id, amount)` - Damage an enemy entity.
  - `AttackAimTarget(damage)` - Melee the nearest aimed enemy.

### `communication`
Core Ã¢â‚¬â€ communication.lua Game toasts / announcer presentation. Chat + voice nest as sub-modules.
- **SystemConfig:** anchor, announcer_enabled, announcer_sfx, color, duration
- **API:** GetGameMessageStyle, DisplayGameMessage
  - `GetGameMessageStyle()` - Current game message style table.
  - `DisplayGameMessage(text, audience)` - Show a toast (prefer Game.Message).

### `crafting`
Sandbox Ã¢â‚¬â€ crafting.lua Recipe tables edited in the Craft Data tab. Runtime craft UI is stubbed.
- **SystemConfig:** enabled, key_craft, recipes
- **API:** IsCraftingEnabled, ListCraftRecipes, TryCraft
  - `IsCraftingEnabled()` - True if crafting pack is enabled.
  - `ListCraftRecipes()` - List craft recipe ids.
  - `TryCraft(recipeId)` - Attempt a recipe by id.

### `harvesting`
Sandbox Ã¢â‚¬â€ harvesting.lua Boots tree/chop harvest (axe Ã¢â€ â€™ wood). Entity logic lives in templates/harvest.lua.
- **SystemConfig:** range, starter_axe
- **API:** TryHarvestAttack
  - `TryHarvestAttack(range)` - Punch/chop nearest harvestable.

### `health`
Game Baseline Ã¢â‚¬â€ health.lua (P1-27 Wave 2+) Per-player HP; void Y + landing impact; HUD styles; configurable On Death.
- **SystemConfig:** consequence, consequence_amount, consequence_id, death_delay, death_script, fall_damage, fall_impact, fall_impact_max, fall_impact_min, fall_impact_mul, fall_y, hud_style, max_hp, on_death, show_hud, units_per_icon
- **API:** OnDeath, SetHealthHudStyle, GetHealth, GetMaxHealth, IsDead, RespawnPlayer, DamageEntity, HealEntity
  - `OnDeath(fn)` - Register a death callback: OnDeath(function(playerId) end).
  - `SetHealthHudStyle(style, units_per_icon)` - Set health HUD style (percent/hearts/bar) and units per icon.
  - `GetHealth(id)` - Current HP for an entity id.
  - `GetMaxHealth()` - Configured max HP.
  - `IsDead(id)` - True if the entity is dead.
  - `RespawnPlayer(id, force_spawn_point)` - Full heal and move to spawn.
  - `DamageEntity(id, amount)` - Apply damage; may trigger On Death.
  - `HealEntity(id, amount)` - Heal an entity by amount.

### `interact`
Game Baseline â€” interact.lua (P1-27 / P1-28) Press use-key near an interactable â†’ kind trigger (message / door / item / chest / menu / sound / custom).
- **SystemConfig:** key_use, range
- **API:** (config only)

### `inventory`
Game Baseline Ã¢â‚¬â€ inventory.lua (P1-28 Wave 3) Item bags + one equipped tool + sandbox hotbar (1Ã¢â‚¬â€œ9 / scroll / click). Systems Ã¢â€ â€™ Inventory: quick_slots (hotbar size, max 9) / inventory_slots (bag kinds).
- **SystemConfig:** inventory_slots, quick_slots
- **API:** GetQuickSlotCount, GetInventorySlotCount, GetItemCount, AssignHotbarItem, SelectHotbarSlot, CycleHotbar, GetSelectedHotbarSlot, RefreshHotbar, AddItem, RemoveItem, HasItem, ListItems, EquipTool, UnequipTool, GetEquippedTool, FormatInventory
  - `GetQuickSlotCount()` - Hotbar slot count.
  - `GetInventorySlotCount()` - Bag capacity (kinds).
  - `GetItemCount(player, item_id)` - Count of an item in the bag.
  - `AssignHotbarItem(player, item_id)` - Put an item id into the hotbar.
  - `SelectHotbarSlot(slot)` - Select hotbar slot 1-9.
  - `CycleHotbar(delta)` - Cycle hotbar selection (+1 / -1).
  - `GetSelectedHotbarSlot(player)` - Current hotbar slot index.
  - `RefreshHotbar(player)` - Push hotbar HUD for a player.
  - `AddItem(player, item_id, amount)` - Add an inventory item.
  - `RemoveItem(player, item_id, amount)` - Remove amount of an item.
  - `HasItem(player, item_id, amount)` - True if bag has at least amount.
  - `ListItems(player)` - List item ids in the bag.
  - `EquipTool(player, item_id, silent)` - Equip a tool from the bag.
  - `UnequipTool(player, silent)` - Unequip the current tool.
  - `GetEquippedTool(player)` - Currently equipped tool id.
  - `FormatInventory(player)` - Human-readable inventory string.

### `menu`
Game Baseline Ã¢â‚¬â€ menu.lua (P1-28 Wave 3) Basic in-game panels: ShowMenu / CloseMenu / inventory sheet (I).
- **SystemConfig:** key_inventory
- **API:** IsMenuOpen, ShowMenu, CloseMenu, OpenInventoryMenu, ToggleInventoryMenu
  - `IsMenuOpen()` - True if a menu panel is open.
  - `ShowMenu(title, body)` - Open a simple menu panel.
  - `CloseMenu()` - Close the open menu.
  - `OpenInventoryMenu()` - Open inventory + resources sheet.
  - `ToggleInventoryMenu()` - Toggle inventory menu.

### `mining`
Sandbox Ã¢â‚¬â€ mining.lua (stub) Digging ore / stone veins will live here. Placeholders so Gather tools can hook later.
- **SystemConfig:** enabled, range, starter_pickaxe
- **API:** MineHit, FindMineTarget, TryMineAttack
  - `MineHit(entityId, player)` - Apply a mine hit (stub).
  - `FindMineTarget(range)` - Find nearest mine target (stub).
  - `TryMineAttack(range)` - Try a mine attack (stub).

### `physics`
Game Baseline â€” physics.lua Apply body types; world gravity comes from systems.json via host. Collision defaults (bounce / friction / slide) live on the Physics module and seed Object Editor props when authors leave fields empty.
- **SystemConfig:** (none)
- **API:** (config only)

### `player_control`
Game Baseline â€” player_control.lua (P1-26) WASD + arrow keys + Space for local player via CharacterMove (whitelist). Hold Run (default Shift) for a speed boost when run_enabled is on. Left-click / F melee is built-in so attack works even without the Combat pack.
- **SystemConfig:** jump_speed, key_back, key_forward, key_jump, key_left, key_right, key_run, run_enabled, run_multiplier, speed, swim_factor, wade_factor
- **API:** (config only)

### `player_management`
Game Baseline â€” player_management.lua (P1-26) Ensure the local player exists as a Kenney character body with walk/idle anims. Extra slots (Player2+) only appear when a peer joins or something explicitly spawns them (AI / lobby seat) â€” never auto-create a solo placeholder.
- **SystemConfig:** (none)
- **API:** (config only)

### `resources`
Game Baseline Ã¢â‚¬â€ resources.lua (P1-28 Wave 3+) Dynamic currency list from Systems Ã¢â€ â€™ Resources Ã¢â€ â€™ items[] (Unity-style array). Each item: { id, amount, color }. hud_anchor: free (xy) | ui_bar (RTS top bar) | inventory (Adventure bag/hotbar).
- **SystemConfig:** hud_anchor, hud_x, hud_y, items, show_hud
- **API:** GetResource, SetResource, AddResource, ListResources, FormatResources
  - `GetResource(player, resource_id)` - Get a currency/resource amount.
  - `SetResource(player, resource_id, amount)` - Set a resource amount.
  - `AddResource(player, resource_id, amount)` - Add to a resource (toast).
  - `ListResources(player)` - List resource ids for a player.
  - `FormatResources(player)` - Human-readable resources string.

### `scoreboard`
Game Baseline Ã¢â‚¬â€ scoreboard.lua Match / round scores. HUD placement is settings-only until chrome lands.
- **SystemConfig:** show_hud, sort, title
- **API:** SetScore, AddScore, GetScore
  - `SetScore(player, amount)` - Set match score for a player.
  - `AddScore(player, amount)` - Add to match score.
  - `GetScore(player)` - Current match score.

### `selection`
Game Baseline â€” selection.lua (RTS) Click-drag marquee + click-add selection. Host chrome lands later; settings boot now.
- **SystemConfig:** additive, box_color, drag_select
- **API:** (config only)

### `simple_ui`
Game Baseline â€” simple_ui.lua (P1-27 Wave 2) Welcome toast + periodic HUD refresh when Health is present.
- **SystemConfig:** hud_refresh, show_welcome
- **API:** (config only)

### `spawn`
Game Baseline â€” spawn.lua (P1-26 / P1-27 team filter) Place local player at per-player spawn, else team spawn, else global spawn_point. Feet are ground-snapped by the host (GetSpawnPosFor / GetSpawnPos).
- **SystemConfig:** (none)
- **API:** (config only)

### `teams`
Game Baseline â€” teams.lua (P1-27 Wave 2) Assign Player1/Player2 team ids; spawn pack uses GetTeamSpawnPos when set.
- **SystemConfig:** player1_team, player2_team
- **API:** (config only)

### `time_scale`
Game Baseline â€” time_scale.lua Multiplier for clock advance (0 = freeze, 1 = normal, >1 = faster days).
- **SystemConfig:** scale
- **API:** (config only)

### `vitality_icons`
Adventure vitality â€” hearts/honeycombs HUD over Core percentage health.
- **SystemConfig:** style, units_per_icon
- **API:** (config only)

### `voice`
Core Ã¢â‚¬â€ voice.lua (stub) Proximity / team / global voice. Capture + net land later.
- **SystemConfig:** enabled, key_ptt, lock_team, max_distance, mode, push_to_talk
- **API:** IsVoiceEnabled, GetVoiceMode, GetVoiceMaxDistance
  - `IsVoiceEnabled()` - True if voice is enabled.
  - `GetVoiceMode()` - Voice mode string.
  - `GetVoiceMaxDistance()` - Voice max distance.

### `worldgen`
Game Baseline â€” worldgen.lua Pushes SystemConfig into global SeedOptions for templates/worldgen.lua.
- **SystemConfig:** (none)
- **API:** (config only)
<!-- END GENERATED -->

## Worked example: Pete triple jump

Floor jump stays with `player_control`; this script only adds mid-air jumps when the Main Menu display name is Pete. Full write-up: `docs/lua-api/examples/triple-jump-pete.md`.

```lua
local MAX_JUMPS = 3
local AIR_IMPULSE = 4.5
local jumps = 0

local function is_pete()
  local name = GetLocalDisplayName()
  return name ~= nil and string.lower(tostring(name)) == "pete"
end

OnTick(function(dt)
  local me = GetLocalPlayer()
  if me ~= nil and me ~= "" and HasEntity(me) and IsOnFloor(me) then
    jumps = 0
  end
end)

OnKey("space", function()
  if not is_pete() then return end
  local me = GetLocalPlayer()
  if me == nil or me == "" or not HasEntity(me) then return end
  if IsOnFloor(me) then
    jumps = 1
    return
  end
  if jumps >= MAX_JUMPS then return end
  jumps = jumps + 1
  CharacterMove(me, 0, 0, AIR_IMPULSE)
end)
```

## Output contract

When writing creator scripts:

1. Use real APIs from the cheat sheets above.
2. Prefer libs (`Game`, `Basic`, `Platform`, `MatchUi`, ...) over raw host calls when both exist.
3. Do not invent host functions or C# classes.
4. Put map-only logic in `scripts/<name>.lua`; call `Include` for shared libs.
