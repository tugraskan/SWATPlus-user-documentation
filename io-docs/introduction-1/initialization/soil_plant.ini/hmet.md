---
description: Intended pointer to the heavy-metal initialization file (read and crosswalked, but not used in main 6f515368)
---

# hmet

**Code reference:** `sol_plt_ini(ii)%hmetc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L135)).

Intended foreign key referencing [name](../hmet_hru.ini/name.md) in [**hmet\_hru.ini**](../hmet_hru.ini/). [`soil_plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_plant_init.f90#L47-L50) reads `hmetc`, and [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L109-L110) resolves it into `sol_plt_ini(isp_ini)%hmet`, which is never subsequently read.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
