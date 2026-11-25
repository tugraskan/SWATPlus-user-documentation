---
description: Ultimate upper limit enforced on a plant soft-calibration parameter.
---

# up

**Code reference:** `pl_prms(i)%prm(ilum)%up` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L161), [clamp](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L145-L515)).

Absolute maximum parameter value (real, struct default `0.`) enforced on `pcom%plcur` fields in [`calsoft_plant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L145-L515) and on the final `init_val` written by [`pl_write_parms_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_write_parms_cal.f90#L38-L50):

$$p = \min(p, u)$$

where $p$ is the calibrated plant parameter value and $u$ is `up`.
