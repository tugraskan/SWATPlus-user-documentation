---
description: "Groundwater evapotranspiration"
---

# gw_et

**Code reference:** `gwet_grid` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_output.f90#L584)); `gw_hyd_grid_mo%gwet` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_module.f90#L120)).

Groundwater consumed by evaporation and plant water uptake.

**Unit:** mm.

The daily exchange is normalized over total basin area. Monthly and yearly values accumulate the daily exchanges; average-annual output gives the mean annual value over the reporting years. Keep the reported sign when combining gains and losses.

[Back to the output table](../gwflow-basin-water-balance.md).
