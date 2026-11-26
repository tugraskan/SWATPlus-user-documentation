---
description: Maximum rooting depth
---

# dp\_tot

**Code reference:** `soildb(isol)%s%zmx` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L67)).

Maximum rooting depth in the soil profile (mm; Fortran struct default: `1500.`). If no maximum rooting depth is specified, the model assumes that roots can develop throughout the entire depth of the soil profile.

In SWAT+ main (`6f515368`) and dev (`aa4179fe`), `dp_tot` is read by [`soil_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_db_read.f90#L65) and copied to `soil%zmx` in [`soils_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L64) ([HRU copy](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L305)), but [`hydro_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydro_init.f90#L127) unconditionally overwrites `soil(j)%zmx = soil(j)%phys(nly)%d` with the bottom depth of the deepest soil layer before simulation begins. During simulation, `soil%zmx` caps plant root depth ([`pl_root_gro.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_root_gro.f90#L34-L35)) and defines profile depth in tile-drainage and water-table routines ([`swr_percmain.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_percmain.f90#L146-L172), [`swr_drains.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_drains.f90#L99-L197)). On dev, planting no longer lowers `soil%zmx` to the plant's rooting depth ([`mgt_plantop.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_plantop.f90#L66-L73)).
