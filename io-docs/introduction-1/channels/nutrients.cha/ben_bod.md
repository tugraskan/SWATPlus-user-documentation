---
description: Benthic oxygen demand rate in the channel at 20ºC
---

# ben\_bod

**Code reference:** `ch_nut(ich)%rk4` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L125)).

Enter this field in mg O2/m2*day. After reading it, SWAT+ divides the value by the number of routing time steps per day to obtain the value used for each routing step.
