---
description: "Object identifier"
---

# obtypno

**Code reference:** `acu_elem(i)%obtypno` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L223), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L174)).

Sequential object identifier (`integer`, dimensionless, default `0`). In [`aqu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L187), it is copied into `acu_cal(ireg)%num(iaqu)`, which is never read afterward.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
