---
description: "Organic-phosphorus delivery ratio for this named record"
---

# sedp

**Code reference:** `dr(ii)%sedp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L35), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_om.f90#L60)).

Dimensionless delivery-ratio multiplier (`fraction`; Fortran struct default: `0.`) for organic phosphorus mass. During hydrograph scaling in [`hydout_mult`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1398), SWAT+ computes:

$$H_{\text{out}} = H_{\text{in}} \cdot r_{\text{sedp}}$$

where $H_{\text{in}}$ is the incoming organic phosphorus load (`kg P`), $r_{\text{sedp}}$ is `dr(ii)%sedp`, and $H_{\text{out}}$ is the delivered load (`kg P`). This ratio is applied to Routing Unit elements in [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L100) ([elements](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L123), excluding recharge at `#L135`) and to standalone `dr` spatial objects in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L361).
