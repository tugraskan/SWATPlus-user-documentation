---
description: The month of the simulation that the reservoir becomes operational
---

# mon\_op

**Code reference:** `res_hyddb(ires)%mores`

**Declared type:** `reservoir_hyd_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_hyd.f90#L49), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L67)).

If 0 is input for [yr\_op](yr_op.md) and _mon\_op_, the model assumes the reservoir is in operation at the beginning of the simulation.
