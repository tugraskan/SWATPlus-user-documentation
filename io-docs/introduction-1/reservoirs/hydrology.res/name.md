---
description: Name of the reservoir hydrology record
---

# name (hydrology.res)

**Code reference:** `res_hyddb(ires)%name`

**Declared type:** `reservoir_hyd_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_hyd.f90#L49), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L65)).

The name of the reservoir hydrology record is a primary key referenced by the foreign key [hyd](../reservoir.res/hyd.md) in [**reservoir.res**](../reservoir.res/). All names in the **hydrology.res** file must be unique.
