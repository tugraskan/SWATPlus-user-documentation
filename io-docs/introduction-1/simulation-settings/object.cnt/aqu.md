---
description: Number of aquifers in the simulation
---

# aqu

**Code reference:** `sp_ob%aqu` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L446)).

Number of 1-D aquifer objects in the simulation (integer; Fortran struct default: `0`). When `aqu > 0`, [`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L144-L147) assigns `sp_ob1%aqu`, reads `aquifer.con`, and reads 2-D aquifer connectivity.

When GWFlow is active (`gwflow = 1` in `codes.bsn`) and `chancell.gw` exists, [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L71-L79) resets `sp_ob%aqu = 0` and disables `aquifer.con` (`in_con%aqu_con = 'null'`).
