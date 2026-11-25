---
description: "Tile depth for this cell, m"
---

# cell_tile_depth_over(i)

**Code reference:** `cell_tile_depth_over(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L194), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L478-L481)).

Optional column 18. Depth of the tile drain below the ground surface, in m. It replaces `tile_depth_val` from [tile.gw](../tile.gw/tile_depth_val.md) for this cell ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1039-L1043)). It is used only when tile drainage is on and the cell is flagged as tiled.
