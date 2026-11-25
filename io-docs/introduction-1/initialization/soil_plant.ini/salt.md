---
description: Pointer to the salt initialization file
---

# salt

**Code reference:** `sol_plt_ini(ii)%saltc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L134)).

Foreign key referencing [name](../salt_hru.ini/name.md) in [**salt\_hru.ini**](../salt_hru.ini/). During setup, [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L116-L117) resolves `saltc` into `sol_plt_ini(isp_ini)%salt`, which [`salt_hru_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_hru_init.f90#L45) uses to initialize HRU soil salt ion concentrations and mineral pools.
