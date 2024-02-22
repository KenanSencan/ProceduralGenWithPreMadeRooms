# Editor Tools

The **Editor Tools** are designed to simplify manual room configuration processes within the plugin. Below are detailed steps on how to utilize these tools effectively.

## Getting Started with Editor Tools

1. **Initiate Tool**: Right-click on any folder within the **Content Browser** (excluding C++ base classes) and select **Make very cool Procedural Map label**. (The plugin will become more professional manner following core optimization and error resolutions.)

   ![Initiate Editor Tool](Images%2FScreenshot%202024-02-20%20032958.png)

2. **Tool Window**: Upon selection, a window displaying all created rooms will appear, featuring:
    - **Label**: The name of each room.
    - **Two Images**: Representing the **Enter** and **Exit** socket directions. For rooms marked as **NoExit**, an `X` image will denote the **Exit Direction**.
    - **Disabled Checkbox**: Indicates whether all tests are passed for a room (future functionality).
    - **Room Selection**: Clicking on a room highlights with yellow color compatible rooms for pairing. Use Shift+Click to select a secondary room, revealing a **Make Test** button.

   ![Room Selection](Images%2FScreenshot%202024-02-20%20034418.png)

3. **Room Manager**: Triggered after selecting two rooms, unless a **NoExit** room is chosen first. Features include:
    - **Spawn Selected Room**: Spawns the first selected room.
    - **Navigation**: Use `W A S D E Q` keys and the **Scroll Wheel** to move and adjust speed within the editor.

   ![Room Manager](Images%2FScreenshot%202024-02-20%20041013.png)

4. **Start Test**: Launches the **Block Tile Selection** window, allowing for detailed configuration:
    - **Open "RoomName"**: Opens the room's Blueprint editor if box extents are incorrect, with tiles outlined by debug boxes.
    - **Start Exclusion**: A button to begin tile exclusion selection, with Shift to select and Ctrl to deselect tiles.
    - **Save Exclusions**: Saves selected exclusions to the blueprint permanently.
    - **Test Overlap**: Tests overlap with the second selected room, indicating success or failure through color coding.
    - **Confirmation Checkbox**: Confirms correct block tile exclusion settings for the first room.

   ![Block Tile Selection](Images%2FScreenshot%202024-02-20%20040058.png)
   ![Overlap Test](Images%2FScreenshot%202024-02-20%20040909.png)

5. **Corridor Scenario Testing**: Initiated by clicking **Make Corridor Test With Selected Two Rooms**, leading to corridor configuration options.

6. **Corridor Scenario Manager**: Allows for corridor path creation between the first and second selected rooms, with functionalities to spawn rooms, adjust paths, and restart operations as needed.

    - **Path Selection**: Navigate to the End Socket, select tiles for the path using Shift, and deselect with Ctrl.
    - **Spawn Room**: Confirms the path and spawns the room, with a message box to indicate if the selected tile direction is incorrect.

   ![Path Selection](Images%2FScreenshot%202024-02-20%20133859.png)

   Upon `Spawn Room` click.

   ![Room Spawn](Images%2FScreenshot%202024-02-20%20134417.png)

Upon successful corridor construction, consider adjusting the Room's [Path Start & End Offsets](References/RoomActor.md#room-actor) to optimize the layout.

These editor tools are designed to streamline the room and corridor configuration process, reducing the need for manual testing and ensuring a smoother development workflow.
