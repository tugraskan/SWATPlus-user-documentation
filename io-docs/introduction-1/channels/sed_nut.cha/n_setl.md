---
description: "Ratio of nitrogen settling to overall sediment settling for the channel reach"
---

# n_setl

**Code reference:** `sd_chd1(idb)%n_setl` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L50)).

Ratio of nitrogen settling to overall sediment settling for the channel reach (struct default `0.5`). Although copied in [`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L108) and exposed in [`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L777), *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
