---
description: "Sediment leaving the channel"
---

# sed_out

**Code reference:** `ch_out_d(ichan)%sed` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L33)).

Daily bulk sediment leaving the channel. Bank erosion and deposition affect this total. The size-class columns follow separate routed masses and can sum to a different value. [Sediment and nutrient calculations](sd-channel-general.md#where-the-sediment-and-nutrient-values-come-from)

**Unit:** tons.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the SD channel general schema](sd-channel-general.md).
