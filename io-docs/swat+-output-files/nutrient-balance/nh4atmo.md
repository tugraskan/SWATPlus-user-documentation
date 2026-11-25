---
description: "Ammonium nitrogen added to the soil by wet and dry atmospheric deposition"
---

# nh4atmo

**Code reference:** `bnb_d%nh4atmo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L98)).

The daily value combines ammonium nitrogen deposited in rain and the day's share of dry deposition. SWAT+ adds it to the ammonium pool in the top soil layer. [Deposition calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/nut_nrain.f90#L43)

**Unit:** kg N/ha for daily, monthly, and yearly rows. The average-annual value is in kg N/ha/year.

See [spatial and time aggregation](README.md#spatial-and-time-aggregation) for how daily values are combined.

[Back to the output table](README.md).
