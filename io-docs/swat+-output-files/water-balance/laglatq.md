---
description: "Water remaining in the lateral routing store"
---

# laglatq

**Code reference:** `bwb_d%laglatq` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L43)).

Daily full-HRU rows read the water left in the lateral routing store after releasing that day's lateral flow. HRU-LTE reports zero. Monthly and yearly rows sum daily store depths. The average-annual row divides those sums by the reporting-year count. [Calculation and reporting details](README.md#water-held-in-routing-stores)

**Unit:** mm.

[Back to the output table](README.md).
