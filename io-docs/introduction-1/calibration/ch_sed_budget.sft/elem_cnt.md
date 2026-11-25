---
description: Channel element indices or ranges in ch_sed_budget.sft.
---

# elem\_cnt

**Code reference:** `elem_cnt(isp)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L23), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_orders_cal.f90#L56)).

List of `nspu` integer tokens identifying SWAT-DEG channels included in the region. Positive values select single channel indices, and negative values define inclusive ranges from the preceding entry (for example, `1 -5` selects channels 1 through 5).
