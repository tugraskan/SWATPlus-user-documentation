---
description: Specific yield of the shallow aquifer
---

# aqu\_sp\_yld

**Code reference:** `hlt_db(i)%sy` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L21)).

Specific yield is the drainable-water volume divided by the total soil or rock volume, so it is dimensionless. SWAT+ main (6f515368) reads this value, but uses it only in calibration parameter handling and calibration output; it does not affect HRU-lte simulation calculations.
