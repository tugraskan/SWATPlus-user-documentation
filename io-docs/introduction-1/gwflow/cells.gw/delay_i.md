---
description: "Recharge delay, days"
---

# delay(i)

**Code reference:** `delay(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L179), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L453)).

Delay, in days, between water leaving the bottom of the soil and reaching the water table. Recharge is lagged each day as ([`gwflow_rech.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_rech.f90#L46-L48)):

$$R_{t} = (1 - e^{-1/\delta}) \, P_{t} + e^{-1/\delta} \, R_{t-1}$$

where $P_{t}$ is the day's percolation from the HRU (mm), $R$ the recharge (mm) and $\delta$ the delay.

The delay is applied per HRU, not per cell ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2195-L2218)). With HRU links, each HRU takes the delay of the last cell listed for it in `hrucell.gw`. With LSU links, every HRU uses the mean delay of all cells. The calibration parameter `aquifer_delay` uses the cell number to index the HRU delays, so it changes the HRU with that number ([`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L1071-L1075)). This is listed in `MODEL_ISSUES.md`.
