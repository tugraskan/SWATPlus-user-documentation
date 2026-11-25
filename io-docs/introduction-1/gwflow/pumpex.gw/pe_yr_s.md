---
description: "First year of the pumping period"
---

# pe_yr_s

**Code reference:** `pe_yr_s` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L139), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L984)).

Calendar year in which the period starts. With [pe_dy_s](pe_dy_s.md), it gives the first pumping day ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L999-L1003)):

$$n_{s} = (y - y_{0}) \times 365 + d$$

where $n_{s}$ is the first pumping simulation day, $y$ is `pe_yr_s` (year), $y_{0}$ is the first simulation year, and $d$ is [pe_dy_s](pe_dy_s.md) (day of year).

A year before the first simulation year gives day 1. The simulation-day counter starts at 1 only when `pumpex.gw` is read; otherwise it starts at 0, so day numbers are one behind ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1011), [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L655)). This is listed in `MODEL_ISSUES.md`.
