---
description: Threshold depth from surface to water table for groundwater flow to occur
---

# flo\_min

**Code reference:** `aqudb(i)%flo_min` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L21)).

Groundwater flow occurs only when the depth from the surface to the water table is less than or equal to _flo\_min_ (m). Otherwise, [`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L110-L116) sets the day's groundwater flow to 0. When flow occurs, it follows the recession equation described in [alpha\_bf](alpha_bf.md).
