---
description: pH value of the soil layer
---

# ph

**Code reference:** `soildb(isol)%ly(j)%ph` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L60)).

Soil pH of the layer (`none`, typically `3–10`; Fortran struct default: `0.0`). During initialization in [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L84), values $\le 10^{-6}$ are replaced with `6.5`. The value can be adjusted via calibration ([`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L346)) and is written to soil-property snapshot outputs ([`soil_nutcarb_write.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L701)), but never enters simulation physics.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
