---
description: Fraction of soil humus that is active
---

# fr\_hum\_act

**Code reference:** `solt_db(isolt)%fr_hum_act`

**Declared type:** `soiltest_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/solt_db_read.f90#L47), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/soil_data_module.f90#L18)).

Fraction of soil humus assigned to the active pool. SWAT+ assigns fr_hum_act times the total pool to active humus and the remaining fraction to stable humus. A value below 1e-9 is replaced with 0.02.
