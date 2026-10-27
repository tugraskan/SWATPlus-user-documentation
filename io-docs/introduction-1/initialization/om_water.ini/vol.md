---
description: Volume of water
---

# vol

**Code reference:** `om_init_water(ichi)%flo`

**Declared type:** `hyd_output` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/om_water_init.f90#L54), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrograph_module.f90#L32)).

Dimensionless initial water fraction. For reservoirs and wetlands, SWAT+ multiplies this value by principal volume. For SWAT-DEG channels, it scales the channel depth used to calculate the initial rating-curve volume.
