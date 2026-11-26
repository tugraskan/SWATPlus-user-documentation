---
description: "Object identifier"
---

# obtypno

**Code reference:** `ccu_elem(i)%obtypno` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L223), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L169)).

Sequential object identifier (`integer`, dimensionless, default `0`). In [`ch_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L182) and [`ch_read_orders_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_orders_cal.f90#L130), it is copied into `ccu_cal%num`, which is never read afterward.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
