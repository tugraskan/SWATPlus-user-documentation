---
description: "Daily leaf area index, summed across plants in a full HRU"
---

# lai

**Code reference:** `bpw_d%lai` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L196)).

The daily full-HRU value sums leaf area index across plants before the day's growth calculation. HRU-LTE reads its current leaf area index after the growth or season-end action. Longer-period rows average the daily values. [Daily calculations](plant-weather-output.md#daily-plant-values)

**Unit:** m2/m2.

[Back to the plant and weather schema](plant-weather-output.md).
