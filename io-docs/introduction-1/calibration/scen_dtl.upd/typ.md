---
description: Update table type in scen_dtl.upd.
---

# typ

**Code reference:** `upd_cond(i)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L48), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_cond_read.f90#L56)).

Intended update table category (up to 25 characters, struct default `""`; source comments list `"lu_change"` and `"hru_fr_change"`).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
