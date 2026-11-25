---
description: Absolute minimum parameter value enforced after a calibration change.
---

# abs\_min

**Code reference:** `cal_parms(i)%absmin` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L1-L12), [clamp](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/chg_par.f90#L52)).

Absolute lower bound (struct default `0.`) passed from [`cal_conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L55) into [`chg_par.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/chg_par.f90#L52), which clamps the updated parameter:

$$p_{\text{new}} = \max(p_{\text{new}}, p_{\min})$$

where $p_{\text{new}}$ is the updated parameter value and $p_{\min}$ is `abs_min`.
