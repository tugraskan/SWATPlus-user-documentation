---
description: "Manning's n roughness coefficient for the main channel"
---

# n

**Code reference:** `ch_hyd(ich)%n` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/channel_data_module.f90#L78)).

Manning's n roughness coefficient for the main channel (struct default `0.05`). Values are clamped to `[0.01, 0.70]` in [`ch_read_hyd.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_hyd.f90#L54-L55).
