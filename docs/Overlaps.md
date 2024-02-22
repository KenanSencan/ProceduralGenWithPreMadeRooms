# Overlaps

Overlap occurs when the area intended for a new room's entrance overlaps with an existing entity, such as another room, a corridor, or a manually placed `BlockRoom` used for overlap testing.

## Testing Overlaps

To test for overlaps, follow these steps:

1. In the ProGen actor's debugging section, specify two room actors in ``Debug Room Sequence``. For this walkthrough, use `Room23` and `Room22` in that order.
      1. The second room must be in the opposite direction of the first room's exit socket direction. For example, if `Room23`'s exit direction is `Vertical Down`, the entrance direction of the second room must be `Vertical Up`.
2. Set the `Number of Rooms` to `2` to limit the spawn to only these two rooms.
3. Specify classes for `Straight Corr Class`, `Turn Corridor Class`, and `BlockCube`.
4. For manual blocking, place a `Block Room` in the overlap area. Use runtime observations to identify potential overlap locations. 
5. In runtime observe the location of the **Second Spawned** room. Copy it's location and place the location at  `Block Room Locations`.

For the given configurations for the ProGen actor, the following results will be given

![Screenshot 2024-02-21 195637.png](Images%2FScreenshot%202024-02-21%20195637.png){width="750"} ![Screenshot 2024-02-21 193108.png](Images%2FScreenshot%202024-02-21%20193108.png){width="500"}


## Handling Overlaps

When an overlap is detected:

1. The room identifies the tiles it will occupy.
2. If any tile is already marked as blocked, the algorithm triggers an overlap resolution process.
3. The algorithm searches outward in a rectangular pattern to find a suitable spawning tile, subject to several conditions:
      1. The intended tiles for room occupation must not be previously occupied.
      2. The room's `End Sockets` must not overlap with any entity. For details, see [End Sockets for Overlap](Overlaps.md#end-socket-overlap).

If these conditions are not met, the algorithm triggers an overlap, relocating the room to the nearest available location.

For successful relocation, the following must hold:

1. The intended occupancy tiles must be unoccupied. (There's no object or room in the intended location)
2. The `End Sockets` must not trigger overlaps. Refer to [End Sockets for Overlap](Overlaps.md#end-socket-overlap) for more information.
3. The [Buffer size](References/ProGenActor.md) must not collide with existing rooms or corridors.
4. There must be sufficient space for corridor path construction, as shown below:

![Path Construction Issue Example](Images%2Fzaza.png)

In this example, even though the room appears to be successfully spawned without any overlap, the lack of space for a corridor path prevents final confirmation of the spawn.

### End Socket Overlap

A room may spawn without overlaps, but if it's too close to a blocking object, making corridor path construction impossible, this is considered an end socket overlap. See the example below:

![End Socket Overlap Example](Images%2FScreenshot%202024-02-19%20234111.png)

In this scenario, the first room spawns correctly, but when the second room attempts to spawn at its end socket, it overlaps with a blocking cube. This prevents corridor path construction, as there's insufficient space for the path.

Further examples demonstrate the issue:

![Path Construction Issue Example 2](Images%2FScreenshot%202023-10-25%20171439.png)

To mitigate this, refer to the [exit socket check](References/RoomActor.md#exit-socket-check) in the Room Actor's details panel and use [Command Prompts](CommandPrompts.md) to assign appropriate exit sockets. (An editor tool for this operation is currently under development.)
