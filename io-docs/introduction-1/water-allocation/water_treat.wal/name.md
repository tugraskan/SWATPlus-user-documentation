---
description: "Record name"
---

# name

**Code reference:** `wtp(iwtp)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L153), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L45)).

25-character name of the water treatment plant (default: `""`). Compared against `wtp_name` in [`wallo_wtps_wuses.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_wtps_wuses.f90#L66) to set `db_num`; however, [`main.f90.in`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L104-L108) calls `wallo_wtps_wuses` before `water_treatment_read`, and `wtp%db_num` is not used in simulation.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
