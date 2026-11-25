---
description: "Last year of the pumping period"
---

# pe_yr_e

**Code reference:** `pe_yr_e` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L139), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L984)).

Calendar year in which the period ends. With [pe_dy_e](pe_dy_e.md), it gives the last pumping day ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1004-L1008)):

$$n_{e} = (y - y_{0}) \times 365 + d$$

where $n_{e}$ is the last pumping simulation day, $y$ is `pe_yr_e` (year), $y_{0}$ is the first simulation year, and $d$ is [pe_dy_e](pe_dy_e.md) (day of year).

A year before the first simulation year gives day 1, so a period that ended before the simulation still pumps on day 1. This is listed in `MODEL_ISSUES.md`.
