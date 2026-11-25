---
description: "Average annual value in the sat_excess column (kg)"
---

# sat_excess

**Code reference:** `sol_grid_satx_tt(s)` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2142), [declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L652)).

**Printed header value:** `sat_excess` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L465)).

This is the 5th value after `name`. For solute `s` the accumulated total is divided by `nbyr_r` before it is written ([division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2121)). The units line prints `kg` for this column ([units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L468-L470)).

**Type:** real (declared `real`, format `e13.4`). **Unit:** kg.

[Back to the output table](../basin-solute-balance.md).
