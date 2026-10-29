---
description: "Mineral phosphorus stored in the aquifer"
---

# minp

**Code reference:** `aqu_d(iaq)%minp` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L45)).

The mineral-phosphorus value printed per unit area. The period aggregation currently sums this value rather than averaging it like nitrate storage.

**Unit:** kg P/ha.

Monthly and yearly entries accumulate the daily printed values. Do not interpret those entries as the mean mass stored during the period.

Basin output weights aquifer values by aquifer area relative to the total basin area.

[Back to the output table](../aquifer.md).
