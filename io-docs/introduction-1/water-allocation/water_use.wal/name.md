---
description: "Record name"
---

# name

**Code reference:** `wuse(iwuse)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L153), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_use_read.f90#L48)).

25-character name of the water-use object (default: `""`). Compared against `wuse_name` in [`wallo_wtps_wuses.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_wtps_wuses.f90#L76) to set `db_num`; however, [`main.f90.in`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L104-L109) calls `wallo_wtps_wuses` before `water_use_read`, and `wuse%db_num` is not used in simulation.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
