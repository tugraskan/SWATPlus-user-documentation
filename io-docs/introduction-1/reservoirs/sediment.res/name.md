---
description: Name of the reservoir and wetland sediment record
---

# name (sediment.res)

**Code reference:** `res_sed(ires)%name` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L99)).

The name of the reservoir and wetland sediment record is a primary key referenced by the foreign keys [sed](../reservoir.res/sed.md) in [**reservoir.res**](../reservoir.res/) and [sed](../../wetlands/wetland.wet/sed.md) in [**wetland.wet**](../../wetlands/wetland.wet/). All names in the **sediment.res** file must be unique.
