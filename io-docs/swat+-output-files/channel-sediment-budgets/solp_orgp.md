---
description: "Phosphorus transferred from soluble to organic phosphorus"
---

# solp_orgp

**Code reference:** `ch_sed_bud(ichan)%solp_orgp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_module.f90#L93)).

Phosphorus transferred from soluble to organic phosphorus.

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

The [channel transformation calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L205) subtracts this mass from the dissolved pool and adds it to the organic pool when `qual2e == 1`. This field is a transfer amount, not the sum of both pools.

[Back to the channel nutrient and sediment budget schema](channel-nutrient-sediment-budget.md).
