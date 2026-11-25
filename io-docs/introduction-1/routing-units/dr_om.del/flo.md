---
description: "Water-flow delivery ratio for this named record"
---

# flo

**Code reference:** `dr(ii)%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L32), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_om.f90#L60)).

Dimensionless delivery-ratio multiplier (`fraction`; Fortran struct default: `0.`) for water-flow volume. During hydrograph scaling in [`hydout_mult`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1395), SWAT+ computes:

$$H_{\text{out}} = H_{\text{in}} \cdot r_{\text{flo}}$$

where $H_{\text{in}}$ is the incoming water volume (`m^3`), $r_{\text{flo}}$ is `dr(ii)%flo`, and $H_{\text{out}}$ is the delivered water volume (`m^3`). This ratio is applied to Routing Unit elements in [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L100) ([elements](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L123), excluding recharge at `#L135`) and to standalone `dr` spatial objects in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L361). For Routing Unit HRU elements using sub-daily Green & Ampt routing, `delrto%flo` also scales the runoff depth-to-flow conversion in [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L235).
