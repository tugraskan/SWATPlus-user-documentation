---
description: "Tile conductivity for this cell"
---

# cell_tile_K_over(i)

**Code reference:** `cell_tile_K_over(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L194), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L486-L489)).

Optional column 20. Tile conductivity for this cell; it replaces `tile_K_val` from [tile.gw](../tile.gw/tile_k_val.md) ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1039-L1043)). It is used only when tile drainage is on and the cell is flagged as tiled.
