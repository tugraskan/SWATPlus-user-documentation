---
description: Number of routing units in the simulation
---

# rtu

**Code reference:** `sp_ob%ru` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L444)).

Number of routing units in the simulation (integer; Fortran struct default: `0`). Read in [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L38). When `rtu > 0`, [`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L137-L141) assigns `sp_ob1%ru` and reads `rout_unit.con`, routing-unit definitions, and routing-unit elements.
