---
description: Aeration stress factor
---

# aeration

**Code reference:** `pldb(ic)%aeration`

**Declared type:** `plant_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_parm_read.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L101)).

Dimensionless aeration-stress threshold used by the plant water-uptake routine when soil water exceeds field capacity. Values less than or equal to zero are replaced by 0.2.
