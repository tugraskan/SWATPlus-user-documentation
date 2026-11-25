---
description: "Average annual value in the gw_sw column (kg)"
---

# gw_sw

**Code reference:** `sol_grid_gwsw_tt(s)` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2141), [declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L650)).

**Printed header value:** `gw_sw` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L464)).

This is the 3rd value after `name`. For solute `s` the accumulated total is divided by `nbyr_r` before it is written ([division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2119)). The units line prints `kg` for this column ([units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L468-L470)).

**Type:** real (declared `real`, format `e13.4`). **Unit:** kg.

[Back to the output table](../basin-solute-balance.md).
