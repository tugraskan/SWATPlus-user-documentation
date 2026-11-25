---
description: Pointer to the pesticide initialization file
---

# pest

**Code reference:** `sol_plt_ini(ii)%pestc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L132)).

Foreign key referencing [name](../pest_hru.ini/name.md) in [**pest\_hru.ini**](../pest_hru.ini/). During setup, [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L95-L96) resolves `pestc` into `sol_plt_ini(isp_ini)%pest`, which [`pesticide_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_init.f90#L57) uses to initialize HRU soil and plant pesticide pools.
