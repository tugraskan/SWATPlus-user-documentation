---
description: "Name of a water-use object"
---

# wuse_name(iwuse)

**Code reference:** `wuse_name(iwuse)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_wtps_wuses.f90#L19), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_wtps_wuses.f90#L59)).

25-character name of a water-use object. Compared against `wuse(:)%name` from [water_use.wal](../water_use.wal/README.md) to set `wuse(iwuse)%db_num` in [`wallo_wtps_wuses.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_wtps_wuses.f90#L74-L81). Because [`main.f90.in`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L104-L109) invokes `wallo_wtps_wuses` before `water_use_read`, `db_mx%uses` is `0` at that point, and `wuse%db_num` is not read in simulation.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
