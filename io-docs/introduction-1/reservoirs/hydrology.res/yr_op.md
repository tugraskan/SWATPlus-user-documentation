---
description: The year of the simulation that the reservoir becomes operational
---

# yr\_op

**Code reference:** `res_hyddb(ires)%iyres`

**Declared type:** `reservoir_hyd_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_hyd.f90#L49), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L66)).

The year specified here must be within the simulation period. If 0 is input for _yr\_op_ and [mon\_op](mon_op.md), the model assumes the reservoir is in operation at the beginning of the simulation.
