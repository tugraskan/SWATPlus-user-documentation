---
description: Organic carbon in aquifer (printed but not used in routing or constituent calculations)
---

# carbon

**Code reference:** `aqudb(i)%cbn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L13)).

Organic carbon content of the aquifer (%). SWAT+ copies this value into `aqu_d%cbn` in [`aqu_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_initial.f90#L178) and writes it to [aquifer output](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_output.f90#L22). Calibration can also change it. No aquifer water, nutrient, or pesticide calculation reads it.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
