---
description: "Leaf area index maximum field, left at zero"
---

# lai_max

**Code reference:** `bpw_d%lai_max` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L217)).

The `lai_max` field starts at zero and stays at zero in all four plant and weather outputs in SWAT+ main `6f515368`. The accumulation operators carry the field forward, and the daily producers leave it at its default. [Record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L217), [HRU daily assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L844-L870), [HRU-LTE daily assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_control.f90#L403-L424).

**Unit:** m2/m2.

[Back to the plant and weather schema](plant-weather-output.md).
