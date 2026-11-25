---
description: "Object index or condition-specific number"
---

# ob_num

**Code reference:** `dtbl_scen(i)%cond(ic)%ob_num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L10)).

Index of the object the condition reads, in the array chosen by the [condition variable](var.md): HRU, reservoir, aquifer, channel, and so on. 0 means the current object that the table is being evaluated for. A few conditions, such as `month`, `jday`, and `year_cal`, do not use it. [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L66-L70) · [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L744-L747) The scenario update loops over every HRU, so 0 means the HRU being processed.
