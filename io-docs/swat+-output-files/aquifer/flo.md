---
description: "Groundwater flow leaving the aquifer"
---

# flo

**Code reference:** `aqu_d(iaq)%flo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L38)).

Water leaving the aquifer as groundwater flow. Read this as an equivalent water depth, not as a discharge rate in cubic metres per second.

**Unit:** mm.

Daily output gives the daily exchange. Monthly and yearly output sum exchanges over the period. Average-annual output gives the mean annual total over the printed simulation years.

Basin output weights aquifer values by aquifer area relative to the total basin area.

[Back to the output table](README.md).
