---
description: "Fixed maximum daily right or duty"
---

# rate_max

**Code reference:** `pou(ipou)%rate_max` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L76), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L70)).

Fixed maximum daily withdrawal rate (`m^3/s`; Fortran struct default: `0.`). In [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L150,L162), SWAT+ converts this rate to daily volume (`m^3/day`) and uses it both as the default daily demand when `dtbl_mx` is `"null"` and as an upper cap when a decision table is active:

$$Q_{\max} = r_{\max} \times 86400, \qquad D_{\text{pou}} = \min\!\left(Q_{\max},\, D_{\text{dtbl}}\right)$$

where $r_{\max}$ is `rate_max` (`m^3/s`), $D_{\text{dtbl}}$ is the decision-table demand `dmd_m3` (`m^3/day`), and $D_{\text{pou}}$ is `pou(ipou)%demand` (`m^3/day`). Note that [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_start_day.f90#L150) overwrites the `"irr"` demand accumulated in [`wallo_start_day.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_start_day.f90#L135-L147) before evaluating `dtbl_mx`.
