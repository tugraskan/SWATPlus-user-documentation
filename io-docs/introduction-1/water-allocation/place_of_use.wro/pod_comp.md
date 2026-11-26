---
description: "Compensation flag if unmet"
---

# comp (POD)

**Code reference:** `pou(ipou)%pod(ipod)%comp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L32), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L98)).

1-character flag (`"y"` or `"n"`; default: `""`) controlling whether this POD can compensate when total POU delivery falls short of total duty. In [`wallo_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_control.f90#L42-L57), for every finished POU with `deliv < duty`, each POD with `comp == "y"` and remaining withdrawal capacity triggers a compensating withdrawal (`wallo_comp = "y"`). On SWAT+ dev that withdrawal is taken from the POD whose controller is running, not necessarily this POD; see [Withdrawal limits and compensation](../../../swat+-output-files/water-allocation/allocation-transactions.md#withdrawal-limits-and-compensation), except channel (`cha`) sources which skip compensation in [`wallo_withdraw.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L75).
