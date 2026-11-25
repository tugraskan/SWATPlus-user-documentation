---
description: Pointer to the reservoir and wetland nutrient file
---

# nut

**Code reference:** `res_dat_c(ires)%nut` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L11)).

The pointer to the reservoir and wetland nutrient file is a foreign key referencing [name](../nutrients.res/name.md) in [**nutrients.res**](../nutrients.res/), matched in [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L152-L154).
