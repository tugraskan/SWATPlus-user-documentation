---
description: "First year of operation"
---

# yr_start

**Code reference:** `yr_start` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L134), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1956)).

Calendar year in which the pond starts operating. The pond starts operating on simulation day ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1958-L1968)):

$$n = (y - y_{0}) \times 365 + \sum_{k < m} D_{k} + d$$

where $y_{0}$ is the first simulation year and $D_{k}$ the days in each month before the start month, with February always 28 days. A start year before $y_{0}$ gives day 1. The simulation-day counter starts at 1 only when `pumpex.gw` is read; otherwise it starts at 0, so day numbers are one behind ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1011), [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L655)). This is listed in `MODEL_ISSUES.md`.
