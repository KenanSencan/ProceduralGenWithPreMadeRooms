# Branching

Branching plays a crucial role in ensuring the uniqueness of map generation. This section uses a large room as an example to illustrate the concept.

![Large Room Example](Images%2FScreenshot%202024-02-20%20140030.png)

In the components section, the `Door Socket Enter` is positioned at the leftmost part of the room, with `Door Socket Exit` placed rightmost exit point. Additional scene components like `Down2`, `Down1`, and `Up` are manually created and located at their respective exit points.

### Configuration Details in Variables Tab

- **Exclusion Arrays**: Specified by `"SceneCompName"_Exclude` arrays, these exclude tiles relative to the scene component's location. For instance, `Up_Exclude` will exclude tiles at the top exit of the room.
- **Offset Arrays**: `"SceneCompName"_Offset` arrays adjust the exclusion arrays' positions. `Up_Offset` modifies the **Up_Exclude** indexes.

Manual configuration of blocking tiles is tedious; utilizing [Editor Tools](SlateEditor.md) is recommended for a more efficient process.

### Room Properties

- Mark the room as `LargeRoom` in the room actor's details pane under [Large Room](References/RoomActor.md#room-actor). If unchecked, the room will not function as a large room.
- For new scene components in a large room, set the component's direction via tags in the detail pane:
    - **StraightUp** for Vertical Up
    - **StraightDown** for Vertical Down
    - **SideRight** for Horizontal Right
    - **SideLeft** for Horizontal Left

The following image will be used for the given examples. Visualizations can be turned on or off.

![BP_ProGen2 Properties](Images%2FScreenshot%202024-02-20%20190137.png)

### Branching Mechanics

- **Number of Rooms**: Specifies the count of normal rooms. For example, with `Number of Rooms` set to 2, additional branch rooms can spawn without counting towards this total. In given map configuration, only Room1, Room11 will be spawned. Max Side Branch Room property will account for total spawned branch rooms.
- **Branch Length**: Determines the amount of room to spawn for each branch, allowing for varied and unique map shapes with even a single LargeRoom.

![Branching Results](Images%2FScreenshot%202024-02-20%20182455.png)
![More Branching Results](Images%2FScreenshot%202024-02-20%20191219.png)

Each initiated branch terminates with a NoExit room, which has an entrance but no exits. The NoExit room's [NoExit property](References/RoomActor.md) must be checked, and its `Door Socket Enter` correctly set.

![NoExit Room Example](Images%2FScreenshot%202024-02-20%20194203.png)

If the initial branch location is unable to spawn, room branch will not be initiated and room's `NoExit` door will be spawned.

![Branching Failure](Images%2FScreenshot%202024-02-20%20194452.png)

- For optimal results, clear the **Debug Room Sequence** and **Block Room Locations**
- Adjust the **Number of Rooms**, **Max Large Room Count**, and **Max Side Branch Room** to suitable values, keeping in mind that too high values for **Max Large Room Count** and **Branch Length** compared **Number Of Rooms** are not recommended.

### Branching Examples

Some branching example for this given configurations  
![Screenshot 2024-02-20 200003.png](Images%2FScreenshot%202024-02-20%20200003.png){width="700"}

If more unique rooms with different branch points are given, it's possible to create much unique and different map patterns. In the **Enter The Gungeon** each level has over 100 different rooms to give unique effect for each playthrough.

![Screenshot 2024-02-20 195551.png](Images%2FFinalExamples%2FScreenshot%202024-02-20%20195551.png){width="200"}
![Screenshot 2024-02-20 195656.png](Images%2FFinalExamples%2FScreenshot%202024-02-20%20195656.png){width="200"}
![Screenshot 2024-02-20 195520.png](Images%2FFinalExamples%2FScreenshot%202024-02-20%20195520.png){width="200"}
![Screenshot 2024-02-20 195719.png](Images%2FFinalExamples%2FScreenshot%202024-02-20%20195719.png){width="200"}
![Screenshot 2024-02-20 195806.png](Images%2FFinalExamples%2FScreenshot%202024-02-20%20195806.png){width="200"}