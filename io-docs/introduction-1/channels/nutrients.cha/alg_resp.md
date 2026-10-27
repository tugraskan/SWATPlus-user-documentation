---
description: Algal respiration rate at 20ºC
---

# alg\_resp

**Code reference:** `ch_nut(ich)%rhoq`

**Declared type:** `channel_nut_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ch_read_nut.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/channel_data_module.f90#L146)).

Enter this field in 1/day. After reading it, SWAT+ divides the value by the number of routing time steps per day to obtain the value used for each routing step.
