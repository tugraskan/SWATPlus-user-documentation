---
description: "Tile conductivity"
---

# tile_K_val

**Code reference:** `tile_K_val` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L108), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1032)).

Tile conductivity for every cell; [cells.gw](../cells.gw/cell_tile_k_over_i.md) can replace it per cell ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1033-L1043)). It is $K_{t}$ in the outflow formula on [tile_depth_val](tile_depth_val.md). The source labels it m/day; because the formula multiplies it by an area and a head difference to give m³/day, it acts as a rate per day. The calibration parameter `tile_K` changes it cell by cell ([`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L1083-L1086)).
