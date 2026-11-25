---
description: "Reservoir exchange from rescell.gw (1 = on)"
---

# res

**Code reference:** `gw_res_flag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L286), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L247)).

1 turns the process on; 0 (or a missing setting) leaves it off. When on and [rescell.gw](../rescell.gw/README.md) exists, water is exchanged between reservoirs and the cells around them. If the file is missing, SWAT+ writes a message and no exchange is simulated ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1109-L1162)).
