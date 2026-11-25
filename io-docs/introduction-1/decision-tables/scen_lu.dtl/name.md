---
description: "Record name"
---

# name

**Code reference:** `dtbl_scen(i)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L29)).

Decision table name, up to 40 characters. [scen_dtl.upd](../../calibration/scen_dtl.upd/) selects tables by this name. The daily update evaluates each selected table for each HRU. [`cal_cond_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_cond_read.f90#L55-L65) · [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L218-L226)
