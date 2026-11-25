---
description: Number of recalls (point sources/inlets) in the simulation
---

# rec

**Code reference:** `sp_ob%recall` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L449)).

Number of recall (point source and inlet) objects in the simulation (integer; Fortran struct default: `0`). Read in [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L38). When `rec > 0`, [`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L161-L163) assigns `sp_ob1%recall` and reads `recall.con`.
