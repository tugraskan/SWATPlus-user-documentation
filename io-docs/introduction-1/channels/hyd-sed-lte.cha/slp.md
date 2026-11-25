---
description: Channel slope
---

# slp

**Code reference:** `sd_chd(idb)%chs` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L23)).

The channel slope is defined as the average slope of the channel along its length (`m/m`), typically calculated by QSWAT+ from the DEM. During initialization ([`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L78-L79)), SWAT+ replaces slopes below `1.0e-9` with `0.000001`. Downcutting bed erosion in [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L275) occurs only when `chs > 0.000001`.
