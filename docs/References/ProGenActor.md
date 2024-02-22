# Reference

## General Map Settings for Procedural Gen

For configuration, navigate to `Plugins -> ProceduralMapGeneration Content -> ProceduralMapGeneration -> BP_ProGen2`.

- **RoomDesigns**: A collection of rooms available for random selection during map generation.
- **NumberOfRooms**: Specifies the total number of rooms to spawn.
- **MaxLargeRoomCount**: Defines the maximum number of large rooms that can be spawned.
- **MapSizeX** and **MapSizeY**: Initial map dimensions. Opting for excessively large sizes may adversely affect performance; thus, default settings are recommended.
- **TileSizeX** and **TileSizeY**: Dimensions of tiles, with 16 being the advised default.
- **Map Center**: The origin point for room spawning, ideally set to (0,0,0).
- **Buffer Size**: The minimum required distance between any two rooms or a room when overlapping occurs, calculated based on tile size and buffer amount.
- **Find corridor path limit**: Limits the adjacent tile checks when attempting to spawn an overlapped room.

---

## Procedural Gen

- **Max Side Branch Room**: Limits the total number of side branch rooms. For details, see [Branching and Large Rooms](../BranchingAndLargeRoom.md#max-side-branch-room).
- **Straight Corr Class**: Assigns the straight corridor actor.
- **Turn Corridor Class**: Assigns the turn corridor actor.
- **Max Move Overlapped Room Iterate**: Here is the critical part completely crippling entire plugin's functionality. [Refer to the Errors page](../Errors.md#max-move-overlapped-room-iterate).

---

## Debugging

- **Debug Room Sequence**: When specified, spawns only the rooms listed in the array, bypassing the procedural generation.
- **Block Room Locations**: Identifies locations for spawning block actors, useful in overlap testing scenarios.
- **Block Room**: The default actor used for blocking; the BlockCube is generally sufficient.
- **Visualize Overlaps**: Highlights blocked areas with yellow debug boxes, useful for identifying blocked tiles but may impact performance.
- **Visualize Visited**: Placeholder for a forgotten functionality.
- **Visualize Begin and End Tiles**: Shows the starting and ending points of corridors in blue boxes for rooms that initially overlapped and were subsequently moved.
- **Visualize Corridor Path**: Outlines the corridor path in red, aiding in corridor pattern analysis.
- **Visualize All Exclusions**: Complements `Visualize Overlaps` by specifically highlighting excluded tiles.
- **Visualize End Socket Overlap Check**: Displays end socket overlaps, with settings adjustable in the [Room Actor](RoomActor.md).
- **Spawn Corridor**: Should always be enabled, with plans for future removal.

---

## Corridor Path Finding

- **Apply Turn Penalty**: Disabling this option omits turn penalties, which are vital for minimizing zigzag patterns.
- **Turn Penalty Amount**: Specifies the penalty for pathfinding turns, with 10 set as the default value.

---

