---
description: "Compensation flag if unmet"
---

# comp (POD)

**Code reference:** `pou(ipou)%pod(ipod)%comp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L32), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L98)).

1-character flag (`"y"` or `"n"`; default: `""`) controlling whether this POD can compensate when total POU delivery falls short of total duty. In [`wallo_control.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_control.f90#L43-L52), if `deliv < duty`, each POD with `comp == "y"` and remaining withdrawal capacity executes a compensating withdrawal (`wallo_comp = "y"`), except channel (`cha`) sources which skip compensation in [`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L75).
