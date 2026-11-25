---
description: Last simulation year for climate adjustments or fourth rdt action index in calibration.cal.
---

# year2

**Code reference:** `cal_upd(i)%year2` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parmchg_read.f90#L68), [use](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L239-L251)).

Ending simulation year index (integer, struct default `0`) for `precip` and `temp` climate adjustments in [`cal_conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L239-L251). For `obj_typ = "rdt"`, a non-zero value selects a fourth action row index at [`cal_conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L158-L160).
