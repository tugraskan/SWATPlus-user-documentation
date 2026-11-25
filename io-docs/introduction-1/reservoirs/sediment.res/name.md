---
description: Name of the reservoir and wetland sediment record
---

# name (sediment.res)

**Code reference:** `res_sed(ires)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L99)).

The name of the reservoir and wetland sediment record is a primary key referenced by the foreign keys [sed](../reservoir.res/sed.md) in [**reservoir.res**](../reservoir.res/) ([`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L140-L141)) and [sed](../../wetlands/wetland.wet/sed.md) in [**wetland.wet**](../../wetlands/wetland.wet/) ([`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L97-L98)). All names in the **sediment.res** file must be unique.
