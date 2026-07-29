# Example: triple jump if display name is Pete

Attach this as a world script (e.g. `scripts/pete_triple_jump.lua`) and `Include` it from `main.lua`, or paste into an entity script. Requires movement host APIs; works with `player_control` by only adding **extra mid-air** jumps.

```lua
-- Pete-only triple jump (floor jump + 2 air jumps).
-- Display name comes from the Main Menu character, not an entity property.

local MAX_JUMPS = 3
local AIR_IMPULSE = 4.5
local jumps = 0

local function is_pete()
  local name = GetLocalDisplayName()
  if name == nil then
    return false
  end
  return string.lower(tostring(name)) == "pete"
end

OnTick(function(dt)
  local me = GetLocalPlayer()
  if me == nil or me == "" or not HasEntity(me) then
    return
  end
  if IsOnFloor(me) then
    jumps = 0
  end
end)

OnKey("space", function()
  if not is_pete() then
    return
  end
  local me = GetLocalPlayer()
  if me == nil or me == "" or not HasEntity(me) then
    return
  end

  -- Floor jump is handled by player_control. Count air jumps only.
  if IsOnFloor(me) then
    jumps = 1
    return
  end

  if jumps >= MAX_JUMPS then
    return
  end
  jumps = jumps + 1

  -- Mid-air impulse: CharacterMove(id, hx, hz, jumpY)
  CharacterMove(me, 0, 0, AIR_IMPULSE)
end)
```

## Notes

- Identity check uses `GetLocalDisplayName()`, not a fictional `Player.Name`.
- `Basic.Jump()` only works on the floor — useless for air jumps.
- If Space feels double-triggered with `player_control`, keep floor jumps to the system and only fire custom logic when `not IsOnFloor(me)`.
