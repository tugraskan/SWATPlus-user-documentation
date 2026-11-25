---
description: Decision-table name in scen_lu.dtl referenced by scen_dtl.upd.
---

# dtbl

**Code reference:** `upd_cond(i)%dtbl` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L49), [crosswalk](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_cond_read.f90#L60-L62)).

Name of the ruleset in [`scen_lu.dtl`](../../decision-tables/scen_lu.dtl/README.md) (up to 25 characters, struct default `""`). [`cal_cond_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_cond_read.f90#L60-L62) matches `dtbl` against `dtbl_scen(icond)%name` (loaded by [`dtbl_scen_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_scen_read.f90#L47)) and stores `cond_num`, which [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L220-L221) evaluates daily.
