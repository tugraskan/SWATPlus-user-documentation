---
description: "Groundwater flow-solution time step"
---

# ts

**Code reference:** `gw_time_step` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/gwflow_module.f90#L8)).

The length of the groundwater flow-solution time step, in days. A daily output row can summarize multiple groundwater solution steps. The printed units row leaves this field unspecified.

**Unit:** days.

This field appears in the daily file only; it is not a column in the monthly, yearly, or average-annual basin water-balance files.

[Back to the output table](../gwflow-basin-water-balance.md).
