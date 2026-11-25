---
description: Pointer to the reservoir and wetland initialization file
---

# init

**Code reference:** `res_dat_c(ires)%init` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L7)).

The pointer to the reservoir and wetland initialization file is a foreign key referencing [name](../initial.res/name.md) in [**initial.res**](../initial.res/), matched in [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L81-L82).
