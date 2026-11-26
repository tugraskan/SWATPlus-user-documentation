---
description: Initial NO3-N concentration in aquifer
---

# no3\_n

**Code reference:** `aqudb(i)%no3` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L11)).

Initial nitrate-N concentration in the aquifer (ppm or mg/L NO3-N). It is used only to set the initial nitrate mass. [`aqu_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_initial.f90#L176) multiplies it by the initial water volume given by [gw\_flo](gw_flo.md), not by aquifer storage.

After that, nitrate is modeled dynamically in [`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L140-L170). Recharge adds nitrate, while lateral groundwater flow, deep seepage, and first-order decay (see [hl\_no3n](hl_no3n.md)) remove it. As a result, groundwater nitrate loads change with both nitrate concentration and groundwater flow.
