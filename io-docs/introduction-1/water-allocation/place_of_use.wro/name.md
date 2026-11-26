---
description: "Name of the place of use"
---

# name

**Code reference:** `pou(ipou)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L68), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L69)).

25-character name identifying the place of use (default: `""`). Written to the daily, monthly, yearly, and average-annual POU totals files (`wallo_met_day`, `wallo_met_mon`, `wallo_met_yr`, `wallo_met_aa`) in [`wallo_pou_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_output.f90#L29-L42).
