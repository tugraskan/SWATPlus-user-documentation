---
description: The month of the simulation that the reservoir becomes operational
---

# mon\_op

**Code reference:** `res_hyddb(ires)%mores` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L67)).

The month of the year (`1–12`; Fortran struct default: `0`, historical table default: `1`) in which the reservoir becomes operational during year [yr\_op](yr_op.md). If `0` is entered for both [yr\_op](yr_op.md) and _mon\_op_, the reservoir is active from the beginning of the simulation.

During initialization ([`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L92-L93)) and daily simulation ([`res_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L43-L44)), the reservoir is active when the current year exceeds `yr_op`, or equals `yr_op` with current month $\ge$ `mon_op`.
