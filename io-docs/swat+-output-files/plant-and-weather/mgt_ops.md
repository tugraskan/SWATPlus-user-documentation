---
description: "Management-operation label written for HRU rows"
---

# mgt_ops

**Code reference:** `lum(ilu)%mgt_ops` ([HRU writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L90)).

HRU rows append this label after `c_gro`. Basin, LSU, and HRU-LTE rows stop at `c_gro` and omit both trailing labels even though the shared header includes them. The missing-value warning applies to those other spatial levels, not to HRU records.

**Unit:** n/a.

[Back to the plant and weather schema](plant-weather-output.md).
