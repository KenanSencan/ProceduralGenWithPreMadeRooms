# Errors

I encourage using the plugin's example rooms and `BP_ProGen2` as provided when troubleshooting.

For technical details, check out the `MoveOverlappedRoom` function within the `ProceduralGen` source code.

When encountering an overlap, the algorithm attempts to find a suitable spawn point by searching outward in a rectangular pattern. However, this process can be time-consuming for spawning just one room. To address this, I've introduced `Max Move Overlapped Room Iterate Normal Room` and `Max Move Overlapped Room Iterate Branch Room`. These settings control the iteration limit for the search loop within the `MoveOverlappedRoom` function. Be mindful that increasing these values can significantly extend the time it takes to spawn a room.

The entire map is structured as a fixed 2D array named `Tiles` within the `ProGen` class. Initially, using a fixed 2D array to represent entire map's structure 
seemed like a straightforward and simple approach. Now, I'm unsure whether this method is too primitive for such a complex algorithm and questioning whether optimization is even possible or not.

I've decided to pause the development of the plugin to further develop my skills in mathematics, algorithms, and optimization techniques.

If you see any potential in this plugin, please don't hesitate to contribute. Your insights and contributions would be greatly appreciated.
