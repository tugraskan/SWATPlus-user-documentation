---
description: USLE P factor
---

# usle\_p

**Code reference:** `cons_prac(icp)%pfac`

**Declared type:** `conservation_practice_table` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cons_prac_read.f90#L45), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/landuse_data_module.f90#L52)).

The USLE P factor is the dimensionless support-practice factor used as a multiplier in the erosion calculation. Enter a value from 0.0 to 1.0; 1.0 means no reduction from a support practice, while lower values reduce modeled erosion proportionally. The default is 1.0.
