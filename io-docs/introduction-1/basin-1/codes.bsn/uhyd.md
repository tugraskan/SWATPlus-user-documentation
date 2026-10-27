---
description: Unit Hydrograph method
---

# uhyd

**Code reference:** `bsn_cc%uhyd`

**Declared type:** `basin_control_codes` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_read_cc.f90#L24), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/basin_module.f90#L53)).

| Code | Option                         |
| ---- | ------------------------------ |
| 0    | Triangular Unit Hydrograph     |
| 1    | Gamma Function Unit Hydrograph |

The Unit Hydrograph method is only relevant when simulating at a sub-daily timestep and [gampt](abstr_init.md) = 0.
