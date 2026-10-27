---
description: Initial deep aquifer flow
---

# aqu\_dp\_flo

**Code reference:** `hlt_db(i)%gwdeep` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_lte_module.f90#L28)).

This value is entered in mm. SWAT+ main (6f515368) reads it, but uses it only in calibration parameter handling and calibration output; it does not initialize the simulated HRU-lte deep-aquifer flow.
