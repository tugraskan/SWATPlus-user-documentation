---
description: Change in SCS Curve Number II value
---

# chg\_cn2

**Code reference:** `fire_db(ifireop)%cn2_upd` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L42), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_fireops.f90#L45)).

Additive change applied to the HRU's SCS Curve Number II (`dimensionless`, default `0.0`; positive values increase surface runoff potential after burning).

In [`pl_burnop.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pl_burnop.f90#L34-L38), SWAT+ adds `chg_cn2` to the current `cn2(j)`, caps the result at `98.0`, and calls [`curno.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/curno.f90#L1-L84) to recompute moisture-condition curve numbers and retention parameters:

$$\text{CN}_{\text{op}} = \min\!\left(\text{CN}_{2} + \Delta\text{CN}_{2},\; 98.0\right)$$

where $\text{CN}_{\text{op}}$ is the updated Curve Number II (dimensionless), $\text{CN}_{2}$ is the current Curve Number II (dimensionless), and $\Delta\text{CN}_{2}$ is `chg_cn2` (dimensionless).
