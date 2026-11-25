---
description: Pointer to the organic-mineral initialization file
---

# org\_min

**Code reference:** `res_init_dat_c(ires)%org_min` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L44)).

The pointer to the organic-mineral initialization file is a foreign key referencing [name](../../initialization/om_water.ini/name.md) in [**om\_water.ini**](../../initialization/om_water.ini/). It is matched in [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L86-L87) and applied in [`res_initial.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_initial.f90#L98-L100) for reservoirs, and matched and applied in [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L54-L55) for wetlands.
