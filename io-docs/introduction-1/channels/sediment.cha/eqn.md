---
description: "Selects the sediment transport equation applied to this channel: 0 = original SWAT"
---

# eqn

**Code reference:** `ch_sed(ich)%eqn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L88)).

Selects the sediment transport equation applied to this channel (`0` = original SWAT, `1` = Bagnold, `2` = Kodatie, `3` = Molinas-WU, `4` = Yang; struct default `0`). Values `<= 0` are set to `0` in [`ch_read_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_sed.f90#L63-L64) and control the clamping range of `cov1` and `cov2`.
