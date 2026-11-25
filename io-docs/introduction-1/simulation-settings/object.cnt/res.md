---
description: Number of reservoirs in the simulation
---

# res

**Code reference:** `sp_ob%res` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L448)).

Number of reservoir objects in the simulation (integer; Fortran struct default: `0`). Read in [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L38). When `res > 0`, [`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L156-L158) assigns `sp_ob1%res` and reads `reservoir.con`.
