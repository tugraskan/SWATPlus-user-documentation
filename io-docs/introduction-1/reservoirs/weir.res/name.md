---
description: Name of the reservoir weir record
---

# name (weir.res)

**Code reference:** `res_weir(ires)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L138)).

The name of the reservoir weir record is referenced by reservoir release actions whose option is `weir` in [**res\_rel.dtl**](../../decision-tables/res_rel.dtl/) (matched in [`dtbl_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_res_read.f90#L84)). It can also be referenced by a scheduled weir management operation in [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L519). All names in `weir.res` must be unique.
