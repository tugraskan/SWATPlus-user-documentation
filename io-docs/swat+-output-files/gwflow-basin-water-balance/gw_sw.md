---
description: "Groundwater discharge to channels"
---

# gw_sw

**Code reference:** `gwsw_grid` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_output.f90#L585)); `gw_hyd_grid_mo%gwsw` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_module.f90#L121)).

Groundwater discharged from aquifer cells to channels.

**Unit:** mm.

The daily exchange is normalized over total basin area. Monthly and yearly values accumulate the daily exchanges; average-annual output gives the mean annual value over the reporting years. Keep the reported sign when combining gains and losses.

[Back to the output table](README.md).
