---
description: "Average annual value in the mineral column (kg)"
---

# mineral

**Code reference:** `sol_grid_minl_tt(s)` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2146), [declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L657)).

**Printed header value:** `mineral` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L466)).

This is the 11th value after `name`. For solute `s` the accumulated total is divided by `nbyr_r` before it is written ([division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L2126)). The units line prints `kg` for this column ([units](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L468-L470)).

**Type:** real (declared `real`, format `e13.4`). **Unit:** kg.

[Back to the output table](../basin-solute-balance.md).
