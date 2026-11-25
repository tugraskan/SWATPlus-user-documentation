---
description: The year of the simulation that the reservoir becomes operational
---

# yr\_op

**Code reference:** `res_hyddb(ires)%iyres` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L66)).

The calendar year in which the reservoir becomes operational (Fortran struct default: `0`; historical table default: `1`, range `1–9999`). If `0` is entered for both _yr\_op_ and [mon\_op](mon_op.md), the reservoir is active from the start of the simulation.

SWAT+ checks operational status during initialization ([`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L92-L93)) and each daily step ([`res_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L43-L44)): the reservoir operates whenever the current calendar year exceeds `yr_op`, or equals `yr_op` with current month $\ge$ `mon_op`.
