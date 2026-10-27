---
description: ​Fraction burned
---

# frac\_burn

**Code reference:** `fire_db(ifireop)%fr_burn`

**Declared type:** `fire_operation` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_read_fireops.f90#L45), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_operations_module.f90#L43)).

Enter the fraction of biomass and surface organic matter burned, from 0.0 to 1.0. SWAT+ uses frac_burn directly for the burned amount and (1 - frac_burn) for the amount remaining. For example, 1.0 represents complete burning and 0.5 represents half; do not enter a percentage.
