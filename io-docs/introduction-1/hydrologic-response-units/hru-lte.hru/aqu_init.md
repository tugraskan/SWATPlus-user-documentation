---
description: Intended initial shallow-aquifer storage (calibration handling and output only)
---

# aqu\_init

**Code reference:** `hlt_db(i)%gw` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L26)).

Intended initial shallow aquifer storage in mm. SWAT+ main (6f515368) reads it, but uses it only in calibration parameter handling and calibration output; it does not initialize the simulated HRU-lte shallow aquifer storage.
