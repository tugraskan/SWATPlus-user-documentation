---
description: Name of the reservoir
---

# name (reservoir.res)

**Code reference:** `res_dat_c(ires)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L6)).

The SWAT+ Editor assigns a name to every object, which is typically the abbreviation of the object type followed by the object number in QSWAT+. It is parsed into `res_dat_c(ires)%name` by [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L74), so the user may change it.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
