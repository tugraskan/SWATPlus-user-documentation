---
description: Name of the reservoir release decision table or control table
---

# rel

**Code reference:** `res_dat_c(ires)%release` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L9)).

Enter the name of a reservoir release decision table in [**res\_rel.dtl**](../../decision-tables/res_rel.dtl/). To use a reservoir control table from [**res\_conds.dat**](../res_conds.dat/), enter its name beginning with `ctbl_`. During input matching in [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L121-L135), SWAT+ looks up `ctbl_` names in `res_conds.dat` and all other names in `res_rel.dtl`.
