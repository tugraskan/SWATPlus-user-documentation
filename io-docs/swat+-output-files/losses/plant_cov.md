---
description: "HRU plant-community identifier; header-only at other written levels"
---

# plant_cov

**Code reference:** `lum(ilu)%plant_cov` ([HRU writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L81)).

HRU rows append this identifier after their numeric balance record. Basin, LSU, and HRU-LTE records omit this value. The shared printed header still includes the label. The missing-value warning applies to those other spatial levels, not to HRU records.

**Unit:** n/a.

[Back to the output table](README.md).
