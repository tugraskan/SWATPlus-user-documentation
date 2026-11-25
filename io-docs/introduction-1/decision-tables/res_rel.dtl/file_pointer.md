---
description: "Selector or referenced record name"
---

# file_pointer

**Code reference:** `dtbl_res(i)%act(iac)%file_pointer` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L25)).

For `release weir` and `release meas`, enter the name of the weir or recall record. For `days` and `dyrt`, this position takes the selector `null`, `pvol`, or `evol`, which select a zero, principal, or emergency base volume. For `dyrt1` it takes `con1`, `con2`, or `con3`. Other options ignore it; enter `null`. A `weir` or `meas` name that matches no record leaves the record index at 0, with no warning. [`dtbl_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_res_read.f90#L76-L97) · [`res_hydro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_hydro.f90#L124-L151)
