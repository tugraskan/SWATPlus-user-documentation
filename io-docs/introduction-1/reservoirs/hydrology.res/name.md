---
description: Name of the reservoir hydrology record
---

# name (hydrology.res)

**Code reference:** `res_hyddb(ires)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L65)).

The name of the reservoir hydrology record is a primary key referenced by the foreign key [hyd](../reservoir.res/hyd.md) in [**reservoir.res**](../reservoir.res/), matched in [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L114-L115). All names in the **hydrology.res** file must be unique.
