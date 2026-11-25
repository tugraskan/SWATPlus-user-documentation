---
description: "Object identifier"
---

# obtypno

**Code reference:** `pcu_elem(i)%obtypno` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L223), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rec_read_elements.f90#L162)).

Sequential object identifier (`integer`, dimensionless, default `0`). In [`rec_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/rec_read_elements.f90#L175), it is copied into `pcu_cal(ireg)%num(irec)`, which is never read afterward.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
