---
description: "Nitrate nitrogen stored in the aquifer"
---

# no3_st

**Code reference:** `aqu_d(iaq)%no3_st` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L44)).

The nitrate-nitrogen mass stored in the aquifer per unit area. This is a stored amount, not a nitrate concentration in water.

**Unit:** kg N/ha.

Daily output gives the daily value. Monthly output averages the daily values; yearly output averages the monthly means. Average-annual output averages the yearly values over the printed simulation years.

Basin output weights aquifer values by aquifer area relative to the total basin area.

[Back to the output table](README.md).
