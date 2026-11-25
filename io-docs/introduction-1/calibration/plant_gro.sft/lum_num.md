---
description: Number of plant target rows in a plant_gro.sft region.
---

# lum\_num

**Code reference:** `plcal(i)%lum_num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calibration_data_module.f90#L274), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_regions_cal.f90#L49)).

Integer count (struct default `0`) of plant-growth target rows following the region line. [`pl_read_regions_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_read_regions_cal.f90#L80-L86) allocates `plcal(i)%lum` to `lum_num` and reads one plant target record per entry.
