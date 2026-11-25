---
description: Drainage coefficient
---

# drain

**Code reference:** `sdr(isdr)%drain_co` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L92)).

Drainage coefficient representing the maximum daily tile drainage rate in millimetres per day (mm/day; default `10.0`, range `10.0–51.0`). It caps daily tile outflow in both the original drawdown equation (`tiledrain = 0` in `codes.bsn`, [`swr_origtile.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_origtile.f90#L28)) and the DRAINMOD equations (`tiledrain = 1`, [`swr_drains.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_drains.f90#L190), [also line 206](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_drains.f90#L206)):

$$q_{\text{tile}} = \min(q_{\text{calc}},\, D_c)$$

where $q_{\text{tile}}$ is the capped daily tile drainage (mm/day), $q_{\text{calc}}$ is the unconstrained drainage rate (mm/day), and $D_c$ is `drain` (mm/day).
