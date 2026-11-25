---
description: "Average depth from ground surface to the water table"
---

# wt_depth

**Code reference:** `depth_wt_avg` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L577)).

The arithmetic mean of ground-surface elevation minus groundwater head across active cells. It is not weighted by cell area.

**Unit:** m.

This field appears in the daily file only; it is not a column in the monthly, yearly, or average-annual basin water-balance files.

[Back to the daily basin water-balance schema](daily-basin-water-balance.md).
