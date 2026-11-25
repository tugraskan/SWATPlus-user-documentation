---
description: "Initial groundwater temperature, °C"
---

# cell_init_temp(i)

**Code reference:** `cell_init_temp(i)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L99), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L496-L498)).

Optional column 23. Initial groundwater temperature of the cell, in °C, used when `heat` is 1 in [codes.gw](../codes.gw/heat.md) ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1494)). If heat transport is on and the column is missing, the cell starts at 0 °C.
