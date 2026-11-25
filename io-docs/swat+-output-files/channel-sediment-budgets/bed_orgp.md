---
description: "Phosphorus deposition or erosion terms"
---

# bed_orgp

**Code reference:** `ch_sed_bud(ichan)%bed_orgp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L91)).

The bed producer multiplies eroded sediment tons by the phosphorus concentration in mg/kg and the fraction `1 - p_bio`. It writes the result without dividing by 1,000. The code does not add this calculated bed load to routed flow. [Nutrient budget calculation](channel-nutrient-sediment-budget.md#how-the-nutrient-values-are-formed).

**Unit:** t × mg/kg as written. Divide by 1,000 for kg.

Monthly and yearly rows sum daily values. The average-annual row divides the accumulated value by the number of printed years.

[Back to the channel nutrient and sediment budget schema](channel-nutrient-sediment-budget.md).
