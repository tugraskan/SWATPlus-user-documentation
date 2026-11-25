---
description: Name of the reservoir and wetland initialization record
---

# name (initial.res)

**Code reference:** `res_init_dat_c(ires)%init` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L43)).

The name of the reservoir and wetland initialization record is a primary key referenced by the foreign keys [init](../reservoir.res/init.md) in [**reservoir.res**](../reservoir.res/) ([`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L81)) and [init](../../wetlands/wetland.wet/init.md) in [**wetland.wet**](../../wetlands/wetland.wet/) ([`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L50)). All names in the **initial.res** file must be unique.
