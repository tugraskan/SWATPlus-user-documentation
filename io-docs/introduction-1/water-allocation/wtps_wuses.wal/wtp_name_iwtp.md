---
description: "Name of a water treatment plant object"
---

# wtp_name(iwtp)

**Code reference:** `wtp_name(iwtp)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_wtps_wuses.f90#L18), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_wtps_wuses.f90#L56)).

25-character name of a water treatment plant object. Compared against `wtp(:)%name` from [water_treat.wal](../water_treat.wal/README.md) to set `wtp(iwtp)%db_num` in [`wallo_wtps_wuses.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_wtps_wuses.f90#L64-L71). Because [`main.f90.in`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L104-L108) invokes `wallo_wtps_wuses` before `water_treatment_read`, `db_mx%treat` is `0` at that point, and `wtp%db_num` is not read in simulation.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
