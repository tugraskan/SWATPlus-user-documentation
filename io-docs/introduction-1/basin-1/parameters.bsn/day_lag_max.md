---
description: Maximum days to lag hydrographs (overwritten with 2 in main 6f515368)
---

# day\_lag\_max

**Code reference:** `bsn_prm%day_lag_mx` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L132), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_prm.f90#L24)).

Maximum number of days (`days`, integer, struct default `0`) used to dimension lagged hydrograph storage arrays for HRUs, routing units, and channels in [`hyd_connect.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L340-L341) and [`flow_hyd_ru_hru.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/flow_hyd_ru_hru.f90#L29-L53).

In SWAT+ main (`6f515368`), [`basin_prm_default.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_prm_default.f90#L60) unconditionally sets `bsn_prm%day_lag_mx = 2` after reading **parameters.bsn**, so any value entered in the file is ignored.
