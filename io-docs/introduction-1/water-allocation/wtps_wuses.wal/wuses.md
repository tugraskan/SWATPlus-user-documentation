---
description: "Number of water-use objects included in the simulation"
---

# wuses

**Code reference:** `wuses` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L5), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_wtps_wuses.f90#L32)).

Number of water-use objects included in the simulation (default: `0`). Used in [`wallo_wtps_wuses.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_wtps_wuses.f90#L35,L45-L51) to allocate `wuse_name`, `wuse_om_stor`, `wuse_om_out`, `wuse_cs_stor`, and `wal_use_om{d,m,y,a}`, and in [`wallo_use_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_use_output.f90#L13) to bound output loops.
