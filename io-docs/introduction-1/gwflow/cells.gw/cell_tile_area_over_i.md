---
description: "Tile drain area for this cell, m²"
---

# cell_tile_area_over(i)

**Code reference:** `cell_tile_area_over(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L194), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L482-L485)).

Optional column 19. Drain area, in m², used in the tile outflow formula for this cell; it replaces `tile_drain_area_val` from [tile.gw](../tile.gw/tile_drain_area_val.md) ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1039-L1043)). It is used only when tile drainage is on and the cell is flagged as tiled.
