---
description: Name of the reservoir and wetland nutrient record
---

# name (nutrients.res)

**Code reference:** `res_nut(ires)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L110)).

The name of the reservoir and wetland nutrient record is a primary key referenced by the foreign keys [nut](../reservoir.res/nut.md) in [**reservoir.res**](../reservoir.res/) ([`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L152-L153)) and [nut](../../wetlands/wetland.wet/nut.md) in [**wetland.wet**](../../wetlands/wetland.wet/) ([`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L110-L111)). All names in the **nutrients.res** file must be unique.
