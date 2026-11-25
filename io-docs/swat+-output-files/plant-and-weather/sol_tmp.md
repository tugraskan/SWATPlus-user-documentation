---
description: "Average temperature of soil layer 2"
---

# sol_tmp

**Code reference:** `bpw_d%sol_tmp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L200)).

For full HRUs, the daily value is the temperature of soil layer 2. Longer periods use a daily mean. HRU-LTE writes zero, which is also the HRU-LTE contribution to LSU and basin values. [Full-HRU assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L849), [HRU-LTE assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L408).

**Unit:** deg C.

[Back to the plant and weather schema](plant-weather-output.md).
