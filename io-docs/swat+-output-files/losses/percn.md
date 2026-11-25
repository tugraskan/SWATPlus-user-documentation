---
description: "HRU nitrate transported by percolation; header-only at other levels"
---

# percn

**Code reference:** `hpw_d(j)%percn` ([daily HRU writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L81)); matching monthly/yearly values and `percn_aa` at average-annual output.

HRU losses rows append nitrate transported by percolation after `plant_cov` and `mgt_ops`. Monthly and yearly rows use the corresponding plant/weather accumulators; the [average-annual write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L274) divides `hpw_a(j)%percn` by printed years. Basin, LSU, and HRU-LTE rows stop at `satexn`, so their printed `percn` heading has no corresponding value.

**Unit:** kg N/ha for daily, monthly, and yearly output. Average annual uses kg N/ha/year.

[Back to the output table](README.md).
