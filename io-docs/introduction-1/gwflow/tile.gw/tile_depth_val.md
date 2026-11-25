---
description: "Tile depth below ground, m"
---

# tile_depth_val

**Code reference:** `tile_depth_val` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L106), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1030)).

Depth of the tile drains below the ground surface, in m, for every cell; [cells.gw](../cells.gw/cell_tile_depth_over_i.md) can replace it per cell ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1033-L1043)). Tile outflow from an active, tiled cell is

$$Q = A_{d} \, K_{t} \, (h - (z - d_{t})) \quad \text{when} \; h > z - d_{t}$$

where $Q$ is the outflow (m³/day), $A_{d}$ the drain area, $K_{t}$ the tile conductivity, $h$ the head, $z$ the ground elevation and $d_{t}$ the tile depth ([`gwflow_tile.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_tile.f90#L45-L56)). The outflow is limited to the water stored in the cell and goes to the channel of the nearest channel cell ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1080-L1100)).
