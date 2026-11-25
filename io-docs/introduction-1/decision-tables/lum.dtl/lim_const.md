---
description: Limit constant
---

# lim\_const

**Code reference:** `dtbl_lum(i)%cond(ic)%lim_const` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L13)).

Number compared with the condition variable, or combined with the [limit variable](lim_var.md) according to [lim_op](lim_op.md). Its unit follows the [condition variable](var.md): for example `res_inflo` is m³/s, `wet_depth` and `weirh` are mm, and `wtow_vol` is a fraction of maximum storage. Integer conditions such as `month` and `jday` truncate it to an integer. [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L312-L322) · [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L733-L815) `days_act` compares the counter with the truncated value plus 2. For `prob_unif` and `prob_unif_lu` this is the last day of the window, and for `plant_gro` the plant's position in the community. [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L190-L193) · [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L259-L260) · [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L486-L496)
