---
description: Name of the reservoir and wetland initialization record
---

# name (initial.res)

**Code reference:** `res_init_dat_c(ires)%init`

**Declared type:** `reservoir_init_data_char` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_init.f90#L51), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L43)).

The name of the reservoir and wetland initialization record is a primary key referenced by the foreign keys [init](../reservoir.res/init.md) in [**reservoir.res**](../reservoir.res/) and [init](../../wetlands/wetland.wet/init.md) in [**wetland.wet**](../../wetlands/wetland.wet/). All names in the **initial.res** file must be unique.
