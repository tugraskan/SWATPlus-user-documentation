---
description: "Bank and bed erosion"
---

# bed_ero

**Code reference:** `ch_sed_bud(ichan)%bed_ero` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L69)).

Calculated bed sediment erosion after applying `wash_bed_fr`. The budget records this value, while the line that would add it to the routed hydrograph is commented out. [Nutrient budget calculation](channel-nutrient-sediment-budget.md#how-the-nutrient-values-are-formed).

**Unit:** tons.

Monthly and yearly rows sum daily values. The average-annual row divides the accumulated value by the number of printed years.

[Back to the channel nutrient and sediment budget schema](channel-nutrient-sediment-budget.md).
