---
description: "Nitrogen deposition or erosion terms"
---

# ch_orgn

**Code reference:** `ch_sed_bud(ichan)%ch_orgn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L78)).

Channel deposition is computed as bank-eroded organic nitrogen times `wash_bed_fr` and `n_dep_enr`. [Nutrient budget calculation](channel-nutrient-sediment-budget.md#how-the-nutrient-values-are-formed).

**Unit:** kg.

Monthly and yearly rows sum daily values. The average-annual row divides the accumulated value by the number of printed years.

[Back to the channel nutrient and sediment budget schema](channel-nutrient-sediment-budget.md).
