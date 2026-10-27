---
description: Floodplain slope
---

# fps

**Code reference:** `sd_chd(idb)%fps`

**Declared type:** `swatdeg_hydsed_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_hydsed_read.f90#L61), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_module.f90#L37)).

Floodplain slope in m/m, used in floodplain cross-section geometry and rating-curve calculations. During initialization, SWAT+ limits fps to the channel slope and replaces values at or below 0.000001 with 0.00001.
