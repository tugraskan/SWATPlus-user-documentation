---
description: "Groundwater flow routed to landscape objects"
---

# flo_ls

**Code reference:** `aqu_d(iaq)%flo_ls` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/aquifer_module.f90#L54)).

The portion of groundwater flow routed to landscape objects such as HRUs or routing units.

**Unit:** mm.

Daily output gives the daily exchange. Monthly and yearly output sum exchanges over the period. Average-annual output gives the mean annual total over the printed simulation years.

Basin output weights aquifer values by aquifer area relative to the total basin area.

[Back to the output table](README.md).
