---
description: Calibration parameter identifier in cal_parms.cal.
---

# name

**Code reference:** `cal_parms(i)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L1-L12), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_read.f90#L42)).

Unique parameter identifier (up to 25 characters, struct default `"default"`). Matched against the `name` column of `calibration.cal` in [`cal_parmchg_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parmchg_read.f90#L82-L84) to resolve `num_db`, `obj_typ`, `abs_min`, and `abs_max`.
