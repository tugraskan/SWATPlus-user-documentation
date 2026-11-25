---
description: Pointer to the pesticide initialization file
---

# pest

**Code reference:** `res_init_dat_c(ires)%pest` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L45)).

The pointer to the pesticide initialization file is a foreign key referencing [name](../../initialization/pest_water.ini/name.md) in [**pest\_water.ini**](../../initialization/pest_water.ini/). It is matched in [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L94-L95) and applied in [`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L107-L111) for reservoirs, and matched in [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L61-L62) for wetlands.
