---
description: Pointer to the reservoir hydrology file
---

# hyd

**Code reference:** `res_dat_c(ires)%hyd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L8)).

The pointer to the reservoir hydrology file is a foreign key referencing [name](../hydrology.res/name.md) in [**hydrology.res**](../hydrology.res/), matched in [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L114-L116).
