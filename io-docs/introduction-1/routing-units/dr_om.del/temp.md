---
description: "Water-temperature delivery field (read but not used)"
---

# temp

**Code reference:** `dr(ii)%temp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L49), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_om.f90#L60)).

The 18th numeric column of `dr(ii)` (Fortran struct default: `0.`), parsed as part of the `hyd_output` record by [`dr_read_om.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_om.f90#L60). During hydrograph multiplication in [`hydout_mult`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1412), SWAT+ copies the incoming temperature directly (`hyd3%temp = hyd1%temp`) and ignores `hyd2%temp`.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
