---
description: Optional list of target object numbers or ranges in calibration.cal.
---

# elements

**Code reference:** `elem_cnt(isp)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L23), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parmchg_read.f90#L75)).

List of `obj_tot` integer tokens appended to a `calibration.cal` record when `obj_tot > 0`. Positive integers select individual object indices, while a negative integer defines an inclusive range from the preceding entry (for example, `1 -5 18` uses `obj_tot = 3` tokens to select 6 elements: 1 through 5 and 18), expanded into `cal_upd(i)%num` at [`cal_parmchg_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parmchg_read.f90#L157-L158).
