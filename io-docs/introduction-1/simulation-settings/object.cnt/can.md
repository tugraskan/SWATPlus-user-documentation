---
description: Number of canals in the simulation
---

# can

**Code reference:** `sp_ob%canal` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L452)).

Number of canal objects in the simulation (integer; Fortran struct default: `0`). Read in [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L38). When `can > 0`, [`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L105-L108) sets `sp_ob1%canal` and increments the object-offset counter `nspu`, but no canal connection file is read and `sp_ob1%canal` is not referenced elsewhere in SWAT+ main (`6f515368`).
