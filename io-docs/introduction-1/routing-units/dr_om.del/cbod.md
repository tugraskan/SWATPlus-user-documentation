---
description: "Carbonaceous biological oxygen demand delivery ratio for this named record"
---

# cbod

**Code reference:** `dr(ii)%cbod` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L41), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_om.f90#L60)).

Dimensionless delivery-ratio multiplier (`fraction`; Fortran struct default: `0.`) for carbonaceous biological oxygen demand mass. During hydrograph scaling in [`hydout_mult`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1404), SWAT+ computes:

$$H_{\text{out}} = H_{\text{in}} \cdot r_{\text{cbod}}$$

where $H_{\text{in}}$ is the incoming CBOD load (`kg`), $r_{\text{cbod}}$ is `dr(ii)%cbod`, and $H_{\text{out}}$ is the delivered load (`kg`). This ratio is applied to Routing Unit elements in [`ru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L100) ([elements](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_control.f90#L123), excluding recharge at `#L135`) and to standalone `dr` spatial objects in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L361).
