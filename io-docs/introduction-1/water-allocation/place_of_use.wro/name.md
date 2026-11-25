---
description: "Name of the place of use"
---

# name

**Code reference:** `pou(ipou)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L68), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L69)).

25-character name identifying the place of use (default: `""`). Written to daily, monthly, yearly, and average-annual water-allocation output files (`water_allo_day`, `water_allo_mon`, `water_allo_yr`, `water_allo_aa`) in [`wallo_pou_output.f90`](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_pou_output.f90#L29,L40,L85,L96,L143,L154,L198,L209).
