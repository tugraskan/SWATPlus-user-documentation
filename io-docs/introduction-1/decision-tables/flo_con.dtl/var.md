---
description: "Keyword naming the quantity tested"
---

# var

**Code reference:** `dtbl_flo(i)%cond(ic)%var` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L8)).

Keyword naming the quantity tested, using the same evaluator as the other decision tables; see the [lum.dtl var page](../lum.dtl/var.md). Typical choices are `month`, `jday`, `tile_flo`, `irr_pou_dmd`, and storage conditions. `days_act`, `prob_unif`, and `prob_unif_lu` need data that only the `lum.dtl` reader fills. An unrecognized keyword is ignored without a warning. [`dtbl_flocon_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_flocon_read.f90#L56-L59) · [`conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditions.f90#L619-L638)
