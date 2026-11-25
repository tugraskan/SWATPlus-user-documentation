---
description: Count of object-selection tokens on a calibration.cal record.
---

# obj\_tot

**Code reference:** `cal_upd(i)%num_tot` ([read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parmchg_read.f90#L75), [defaults](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parmchg_read.f90#L106-L151)).

Integer count (struct default `0`) of object-selection tokens trailing on the parameter-change line. When `obj_tot > 0`, SWAT+ reads `obj_tot` integers into `elem_cnt` at [`cal_parmchg_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parmchg_read.f90#L75). When `obj_tot == 0`, [`cal_parmchg_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parmchg_read.f90#L106-L151) automatically selects all objects matching the parameter's `obj_typ` in `cal_parms.cal`.
