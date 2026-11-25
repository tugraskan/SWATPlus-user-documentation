---
description: Maximum execution count in scen_dtl.upd.
---

# max\_hits

**Code reference:** `upd_cond(i)%max_hits` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L46), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_cond_read.f90#L56)).

Intended maximum number of times the referenced update table may execute during the simulation (integer, struct default `0`).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
