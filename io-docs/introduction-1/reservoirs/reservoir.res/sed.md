---
description: Pointer to the reservoir and wetland sediment file
---

# sed

**Code reference:** `res_dat_c(ires)%sed` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L10)).

The pointer to the reservoir and wetland sediment file is a foreign key referencing [name](../sediment.res/name.md) in [**sediment.res**](../sediment.res/), matched in [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L140-L144).
