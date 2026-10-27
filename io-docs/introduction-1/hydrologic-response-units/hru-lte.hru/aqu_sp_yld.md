---
description: Specific yield of the shallow aquifer
---

# aqu\_sp\_yld

**Code reference:** `hlt_db(i)%sy`

**Declared type:** `swatdeg_hru_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_lte_read.f90#L117), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_lte_module.f90#L21)).

Specific yield is the drainable-water volume divided by the total soil or rock volume, so it is dimensionless. SWAT+ main (6f515368) reads this value, but uses it only in calibration parameter handling and calibration output; it does not affect HRU-lte simulation calculations.
