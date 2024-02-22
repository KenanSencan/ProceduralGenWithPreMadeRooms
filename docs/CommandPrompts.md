# Command Prompts

Configuring exclusions and path offsets for each room can be a complex and time-consuming process. The **[Enter Exclusions](References/RoomActor.md#exclusions)** attribute, for example, requires relative **FIntPoint** values based on the **Door Socket Enter** location to determine which tiles should not be blocked. This manual process can be streamlined using command prompts to quickly generate **FIntPoint** data.

## Directions for Relative Tile Selection

Each direction corresponds to an **FIntPoint** value:

- Up = `(X=0, Y=-1)`
- Down = `(X=0, Y=1)`
- Right = `(X=1, Y=0)`
- Left = `(X=-1, Y=0)`

---

## Command Line Usage

The plugin includes several commands to facilitate tile selection and configuration:

- **GoRight**: Copies `(X=1, Y=0)` to the clipboard.
- **GoLeft**: Copies `(X=-1, Y=0)` to the clipboard.
- **GoDown**: Copies `(X=0, Y=1)` to the clipboard.
- **GoUp**: Copies `(X=0, Y=-1)` to the clipboard.

These commands copy their corresponding **FIntPoint** data to the clipboard in a platform-agnostic manner. If **FIntPoint** data is already present in the clipboard, executing a command will update the clipboard with the new summed value. For example:

- Initial clipboard data: `(X=100, Y=100)`.
- After executing **GoRight**: Clipboard updates to `(X=101, Y=100)`.
- After executing **GoDown**: Clipboard updates to `(X=101, Y=101)`.

### CopyGrid Command

The `CopyGrid 'Number' x 'Number'` command copies a specified 2D array to the clipboard. For instance:

`CopyGrid 3x3` will copy the following array to the clipboard: `((X=0, Y=0), (X=0, Y=1), (X=0, Y=2), (X=1, Y=0), (X=1, Y=1), (X=1, Y=2), (X=2, Y=0), (X=2, Y=1), (X=2, Y=2))`.

This command allows users to generate and copy 2D **FIntPoint** arrays, which can then be pasted into the [**Enter & Exit Exclusions**](References/RoomActor.md#exclusions) or [Exit Socket Checks](References/RoomActor.md#exit-socket-check) attributes.

### Utilizing Command Prompts for Offsetting

While specifying exclusion tiles, you may need to adjust their offsets. The **GoUp**, **GoDown**, **GoLeft**, and **GoRight** commands are useful for quickly modifying the entire set of exclusion tiles. However, these operations still require manual verification.

For more efficient and reliable configuration, using [Editor Tools](SlateEditor.md) is recommended. These tools provide a user-friendly interface for adjusting room settings directly within the editor, significantly reducing the need for manual testing.
