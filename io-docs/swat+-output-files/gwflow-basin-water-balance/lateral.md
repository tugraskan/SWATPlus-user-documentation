---
description: "Net lateral flow between groundwater cells"
---

# lateral

**Code reference:** `latl_grid` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_output.f90#L589)); `gw_hyd_grid_mo%latl` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_module.f90#L125)).

The signed sum of lateral groundwater exchanges between cells. This basin sum is a net exchange, not the sum of all positive intercell transfers.

**Unit:** mm.

The daily exchange is normalized over total basin area. Monthly and yearly values accumulate the daily exchanges; average-annual output gives the mean annual value over the reporting years. Keep the reported sign when combining gains and losses.

[Back to the output table](../gwflow-basin-water-balance.md).
