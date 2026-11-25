---
description: "Number of point-of-diversion (POD) records"
---

# imax

**Code reference:** `imax / db_mx%wallo_pod` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L19), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L199-L200)).

Total number of POD records in `point_of_diver.wro` (stored in `db_mx%wallo_pod`). Allocates `pod` and `podd_om`–`poda_om` in [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L205-L209) and bounds the unlimited-source POD loop in [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L119).
