---
description: "Tile drainage from tile.gw (1 = on)"
---

# tile

**Code reference:** `gw_tile_flag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L268), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L246)).

1 turns the process on; 0 (or a missing setting) leaves it off. When on and [tile.gw](../tile.gw/README.md) exists, groundwater above the tile drains of flagged cells flows to channels. If the file is missing, SWAT+ writes a message and sets the setting to 0 ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1020-L1106)).
