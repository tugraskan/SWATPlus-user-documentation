---
description: Pointer to the nutrient initialization file
---

# nutrients

**Code reference:** `sol_plt_ini(ii)%nutc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L131)).

Foreign key referencing [name](../../soils/nutrients.sol/name-nutrients.sol.md) in [**nutrients.sol**](../../soils/nutrients.sol/). During setup, [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L88-L89) resolves `nutc` into the index `sol_plt_ini(isp_ini)%nut`, which [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L43) uses to initialize HRU soil nutrients and carbon pools.
