---
description: Number of herds in the simulation (not used)
---

# hrd

**Code reference:** `sp_ob%herd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L457)).

Number of herd objects in the simulation (integer; Fortran struct default: `0`). Read as part of `sp_ob` in [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L38).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
