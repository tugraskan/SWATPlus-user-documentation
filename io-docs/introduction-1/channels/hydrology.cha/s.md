---
description: "Average longitudinal slope of the main channel"
---

# s

**Code reference:** `ch_hyd(ich)%s` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L76)).

Average longitudinal slope of the main channel (`m/m`, struct default `0.01`). Values `<= 0.` are replaced with `0.0001` in [`ch_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_hyd.f90#L53).
