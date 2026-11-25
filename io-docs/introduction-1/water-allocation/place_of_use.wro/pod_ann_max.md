---
description: "Maximum withdrawal rate cap"
---

# ann_max (POD)

**Code reference:** `pou(ipou)%pod(ipod)%ann_max` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L26), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L98)).

Maximum withdrawal cap (`m^3/s`; Fortran struct default: `0.`). Copied into `wdraw_max` at [`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L164) and checked before initial and compensating withdrawals in [`wallo_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_control.f90#L24,L46):

$$W_{\text{cur}} < W_{\max} \times 86400$$

where $W_{\text{cur}}$ is cumulative withdrawal `wdraw_cur` (`m^3`) and $W_{\max}$ is `wdraw_max` (`m^3/s`). Note that `wdraw_cur` accumulates across days until reset at year-end in [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L378-L380) when `dtbl_wdraw == "null"`, whereas the `86400` factor scales `m^3/s` to one day rather than one year.
