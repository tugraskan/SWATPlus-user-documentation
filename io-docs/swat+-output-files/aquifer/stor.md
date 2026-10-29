---
description: "Water stored in the aquifer"
---

# stor

**Code reference:** `aqu_d(iaq)%stor` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L40)).

The amount of water stored in the aquifer, expressed as an equivalent water depth over its area.

**Unit:** mm.

Daily output gives the daily value. Monthly output averages the daily values; yearly output averages the monthly means. Average-annual output averages the yearly values over the printed simulation years.

Basin output weights aquifer values by aquifer area relative to the total basin area.

[Back to the output table](README.md).
