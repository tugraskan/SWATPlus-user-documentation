---
description: "Dissolved oxygen leaving the channel"
---

# dox_out

**Code reference:** `ch_out_d(ichan)%dox` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L42)).

The water-quality routine assigns dissolved oxygen mass using the adjusted inlet volume. It clears the outlet hydrograph when the computed depth is zero or negative. [Sediment and nutrient calculations](sd-channel-general.md#where-the-sediment-and-nutrient-values-come-from)

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the SD channel general schema](sd-channel-general.md).
