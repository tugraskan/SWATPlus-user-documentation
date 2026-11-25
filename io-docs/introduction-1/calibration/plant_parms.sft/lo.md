---
description: Ultimate lower limit enforced on a plant soft-calibration parameter.
---

# lo

**Code reference:** `pl_prms(i)%prm(ilum)%lo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L160), [clamp](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L146-L516)).

Absolute minimum parameter value (real, struct default `0.`) enforced on `pcom%plcur` fields in [`calsoft_plant.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_plant.f90#L146-L516) and on the final `init_val` written by [`pl_write_parms_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_write_parms_cal.f90#L39-L51):

$$p = \max(p, l)$$

where $p$ is the calibrated plant parameter value and $l$ is `lo`.
