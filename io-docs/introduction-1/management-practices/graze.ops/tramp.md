---
description: Currently not used
---

# bm\_tramp

**Code reference:** `grazeop_db(igrazop)%tramp`

**Declared type:** `grazing_operation` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_read_grazeops.f90#L49), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L127)).

SWAT+ main (6f515368) reads this value and calculates a trampling fraction, but immediately resets that fraction to zero before changing any plant biomass. Changing bm_tramp currently has no effect on simulation results.
