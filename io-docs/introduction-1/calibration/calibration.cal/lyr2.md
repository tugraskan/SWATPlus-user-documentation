---
description: Last soil layer or second reservoir decision-table action index in calibration.cal.
---

# lyr2

**Code reference:** `cal_upd(i)%lyr2` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parmchg_read.f90#L68), [use](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L117-L140)).

Last soil layer index (integer, struct default `0`) for parameters with `obj_typ = "sol"`. [`cal_conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L117-L119) clamps `cal_lyr2` to `soil(ielem)%nly` (and defaults `0` to the bottom soil layer).

For reservoir decision-table parameters (`obj_typ = "rdt"`, `drawdown_days` or `withdraw_rate`), a non-zero `lyr2` supplies a second action row index at [`cal_conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L138-L140).
