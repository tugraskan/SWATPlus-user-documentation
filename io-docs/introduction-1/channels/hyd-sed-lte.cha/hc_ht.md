---
description: Phosphorus concentration in channel bank and bed
---

# p\_conc

**Code reference:** `sd_chd(idb)%p_conc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L40)).

Phosphorus concentration in channel bank and bed material, entered in mg/kg (default `0.30`). SWAT+ uses it in [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L242-L244) to calculate particulate and soluble phosphorus associated with eroded bank sediment. (The bed-erosion addition at [`sd_channel_sediment3.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_sediment3.f90#L292-L298) is commented out.)
