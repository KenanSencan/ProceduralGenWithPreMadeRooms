# Room Actor

The Room Actor settings are crucial for defining room characteristics and behaviors within the procedural generation process.

- **Large Room**: Marking a room as a "Large Room" categorizes it for specific branching behaviors. For detailed information, refer to [Branching and Large Room](../BranchingAndLargeRoom.md#large-room).
- **No Exit**: Indicates rooms that have an entrance but lack an exit. Such rooms are  used to terminate branches in a large room scenario.
- **Path Start Offset** & **Path End Offset**: Adjusts the starting or ending points of corridors to avoid overlaps. For more details, see [Overlaps](../Overlaps.md).
- **Visualize Blocked**: Enables visualization of blocked tiles within the room, aiding in the configuration process.
- **Enter Socket Direction** & **Exit Socket Direction**: Specifies the orientation of the room's entrance and exit. Ensure alignment with the room's physical layout. For configuration guidance, refer to [Getting Started](../index#setting-enter-and-exit-directions-of-the-room).

---

## Door Configuration

- **Enter Door**: Select and spawn the door actor at the `Door Socket Enter` location to define the room's entrance.
- **Exit Door**: Similarly, select and spawn the door actor at the `Door Socket Exit` location to establish the room's exit.

---

## Exclusions

- **Enter Exclusions** and **Exit Exclusions**: Define tiles to be excluded from room placement or corridor connections using `FIntPoint` values. Manual entry is not recommended; instead, use the [Slate Editor](../SlateEditor.md) for a more intuitive configuration process.

## Exit Socket Check

Occasionally, a room may spawn without overlap, yet its placement impedes the spawning of subsequent rooms due to insufficient space for corridor connection. This scenario necessitates careful consideration of exit socket positions to ensure connectivity.

![Exit Socket Check Example](..%2FImages%2FScreenshot%202024-02-19%20234111.png)

In the illustrated example, despite the absence of overlap for the first room, the attempted placement of a second room results in a conflict, illustrating the importance of exit socket checks. For comprehensive guidance, refer to [Slate](../SlateEditor.md).

- **Exit Socket Checks**: Specifies tiles around exit sockets that must remain clear to allow for corridor initiation, defined using `FIntPoint`.
- **Exit Socket Check Offset**: Adjusts the positioning of tiles designated by "Exit Socket Checks" to mitigate potential overlap issues. For additional information, consult [Overlapping](../Overlaps.md).

