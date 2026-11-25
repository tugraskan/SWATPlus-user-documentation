---
description: Average flow distance to stream or object (not used in simulation calculations)
---

# flo\_dist

**Code reference:** `aqudb(i)%flo_dist` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L14)).

Average flow distance (m) from the aquifer to the receiving stream or object. The value is read, copied into the aquifer data, and can be changed through [calibration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L956). No aquifer routing or transport calculation uses it.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
