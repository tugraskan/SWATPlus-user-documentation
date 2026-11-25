---
description: "Nitrogen deposition or erosion terms"
---

# bed_orgn

**Code reference:** `ch_sed_bud(ichan)%bed_orgn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L80)).

The bed producer multiplies eroded sediment tons by the nitrogen concentration in mg/kg and writes the result without dividing by 1,000. The code does not add this calculated bed load to routed flow. [Nutrient budget calculation](channel-nutrient-sediment-budget.md#how-the-nutrient-values-are-formed).

**Unit:** t × mg/kg as written. Divide by 1,000 for kg.

Monthly and yearly rows sum daily values. The average-annual row divides the accumulated value by the number of printed years.

[Back to the channel nutrient and sediment budget schema](channel-nutrient-sediment-budget.md).
