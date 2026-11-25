---
description: Number of HRU element-list tokens in plant_gro.sft.
---

# nspu

**Code reference:** `nspu` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_regions_cal.f90#L18), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_regions_cal.f90#L49-L54)).

Integer count of HRU element-list tokens trailing on the region line. When `nspu > 0`, [`pl_read_regions_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_regions_cal.f90#L53-L54) backspaces and reads `nspu` integers into `elem_cnt`.
