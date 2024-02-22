# Essential Checklist 

To start generating maps all the generation scenarios must be covered. For instance if a room expects a certain direction but there's not any room provides the direction, map will not be generated.

The Directions will be represented as these images. 


[Up]: Images%2FDirections%2FDown.png
[Down]: Images%2FDirections%2FUp.png
[Left]:  Images%2FDirections%2FRight.png
[Right]: Images%2FDirections%2FLeft.png
[NoExit]: Images/Directions/NoExit.png

| Direction        | Image |
|------------------| --- |
| Horizontal Right | ![Left.png][Left] |
| Horizontal Left  | ![Right.png][Right] |
| Vertical Down    | ![Up.png][Up] |
| Vertical Up      | ![Down.png][Down] |
| No Exit          | ![NoExit.png][NoExit] |

The images and their corresponding directions might felt inverted, but they are not inverted. Consider this room example. 

![Screenshot 2024-02-21 150647.png](Images%2FScreenshot%202024-02-21%20150647.png)

When ![Right.png][Right] ![Right.png][Left] is used, it means The room's Door socket Enter starts with **Horizontal Right** and ends with **Horizontal left**.

| For Socket Enter Horizontal Right ![Left.png][Left] | Images                                |
|-----------------------------------------------------|---------------------------------------|
| Left then Left                                      | ![Left.png][Left] ![Left.png][Left]   |
| Left then Up                                        | ![Left.png][Left] ![Up.png][Up]       |
| Left then Down                                      | ![Left.png][Left] ![Down.png][Down]   |
| Left then Right                                     | ![Left.png][Left] ![Right.png][Right] |

| For Socket Enter Horizontal Left ![Right.png][Right] | Images                                  |
|------------------------------------------------------|-----------------------------------------|
| Right then Right                                     | ![Right.png][Right] ![Right.png][Right] |
| Right then Up                                        | ![Right.png][Right] ![Up.png][Up]       |
| Right then Down                                      | ![Right.png][Right] ![Down.png][Down]   |
| Right then Left                                      | ![Right.png][Right] ![Left.png][Left]   |

| For Socket Enter Vertical Down ![Up.png][Up] | Images                               |
|----------------------------------------------|--------------------------------------|
| Up then Up                                   | ![Up.png][Up] ![Up.png][Up]          |
| Up then Right                                | ![Up.png][Up] ![Right.png][Right]    |
| Up then Left                                 | ![Up.png][Up] ![Left.png][Left]      |
| Up then Down                                 | ![Up.png][Up] ![Down.png][Down]      |

| For Socket Enter Vertical Up ![Down.png][Down] | Images                                |
|------------------------------------------------|---------------------------------------|
| Down then Down                                 | ![Down.png][Down] ![Down.png][Down]   |
| Down then Right                                | ![Down.png][Down] ![Right.png][Right] |
| Down then Left                                 | ![Down.png][Down] ![Left.png][Left]   |
| Down then Up                                   | ![Down.png][Down] ![Up.png][Up]       |

| For Socket Exit with No Exit ![NoExit.png][NoExit] | Images                                    |
|----------------------------------------------------|-------------------------------------------|
| Right then No Exit                                 | ![Right.png][Right] ![NoExit.png][NoExit] |
| Left then No Exit                                  | ![Left.png][Left] ![NoExit.png][NoExit]   |
| Up then No Exit                                    | ![Up.png][Up] ![NoExit.png][NoExit]       |
| Down then No Exit                                  | ![Down.png][Down] ![NoExit.png][NoExit]   |

___
## Room Actor

- Each room actor's **[Path Start](References/RoomActor.md#room-actor)** and **[Path End](References/RoomActor.md#room-actor)** offsets must be correctly configured to construct the corridors correctly.
- Each room's [Exit Socket Check](References/RoomActor.md#exit-socket-check) should be configured to trigger correctly when `End Socket` blocked.