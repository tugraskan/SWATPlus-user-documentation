---
description: "Depth from the ground surface to the water table"
---

# dep_wt

**Code reference:** `aqu_d(iaq)%dep_wt` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L39)).

The vertical distance from the representative ground surface to the aquifer water table.

**Unit:** m.

Daily output gives the daily value. Monthly output averages the daily values; yearly output averages the monthly means. Average-annual output averages the yearly values over the printed simulation years.

Basin output weights aquifer values by aquifer area relative to the total basin area.

[Back to the output table](README.md).
