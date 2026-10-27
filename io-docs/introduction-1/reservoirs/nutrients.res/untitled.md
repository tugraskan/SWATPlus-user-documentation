---
description: Name of the reservoir and wetland nutrient record
---

# name (nutrients.res)

**Code reference:** `res_nut(ires)%name` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L110)).

The name of the reservoir and wetland nutrient record is a primary key referenced by the foreign keys [nut](../reservoir.res/nut.md) in [**reservoir.res**](../reservoir.res/) and [nut](../../wetlands/wetland.wet/nut.md) in [**wetland.wet**](../../wetlands/wetland.wet/). All names in the **nutrient.res** file must be unique.
