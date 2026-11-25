---
description: "Length of the main channel within the subbasin"
---

# l

**Code reference:** `ch_hyd(ich)%l` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L77)).

Length of the main channel within the subbasin (`km`, struct default `0.1`). Values `<= 0.` are replaced with `0.0010` in [`ch_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_hyd.f90#L56).
