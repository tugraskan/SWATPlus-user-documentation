---
description: Delivery ratio name (read but not used by the model)
---

# dlr (rout\_unit.rtu)

**Code reference:** `ru(i)%dbsc%elem_dr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_module.f90#L13)).

This column is parsed as a 16-character string into the second component of `ru(i)%dbsc` in [`ru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read.f90#L230). Actual routing-unit element delivery ratios are configured per element via [dlr](../untitled-2/dlr-rout_unit.ele.md) in [**rout\_unit.ele**](../untitled-2/).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
