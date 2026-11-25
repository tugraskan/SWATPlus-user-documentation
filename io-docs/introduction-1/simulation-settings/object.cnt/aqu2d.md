---
description: Number of 2-D aquifers in the simulation (not used)
---

# aqu2d

**Code reference:** `sp_ob%aqu2d` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L456)).

Number of 2-D aquifer objects in the simulation (integer; Fortran struct default: `0`). Read as part of `sp_ob` in [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L38).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
