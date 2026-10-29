---
description: "Groundwater exchange with reservoirs"
---

# reservoir

**Code reference:** `resv_grid` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_output.f90#L595)); `gw_hyd_grid_mo%resv` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_module.f90#L132)).

Signed groundwater exchange with reservoirs.

**Unit:** mm.

The daily exchange is normalized over total basin area. Monthly and yearly values accumulate the daily exchanges; average-annual output gives the mean annual value over the reporting years. Keep the reported sign when combining gains and losses.

[Back to the output table](README.md).
