---
description: "Change in horizontal distance per unit of vertical change on the channel side slope"
---

# side

**Code reference:** `ch_hyd(ich)%side` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L82)).

Change in horizontal distance per unit of vertical change on the channel side slope (dimensionless, struct default `0.0`). Values `<= 1.0e-6` are replaced with `2.0` in [`ch_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_hyd.f90#L58).
