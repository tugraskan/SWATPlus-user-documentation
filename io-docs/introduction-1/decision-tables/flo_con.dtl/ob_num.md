---
description: "Object index or condition-specific number"
---

# ob_num

**Code reference:** `dtbl_flo(i)%cond(ic)%ob_num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L10)).

Index of the object the condition reads, in the array chosen by the [condition variable](var.md): HRU, reservoir, aquifer, channel, and so on. 0 means the current object that the table is being evaluated for. A few conditions, such as `month`, `jday`, and `year_cal`, do not use it. [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L66-L70) · [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L744-L747) In saturated-buffer tables the current object is the source HRU. For `dtbl_mx` and `dtbl_pod_fr` the water allocation routine does not set a current object for the table first, so enter a positive number for object conditions there. [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_start_day.f90#L152-L171) · [`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L637-L643)
