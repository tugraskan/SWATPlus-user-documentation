---
description: Intended initial shallow-aquifer flow (calibration handling and output only)
---

# aqu\_sh\_flo

**Code reference:** `hlt_db(i)%gwflow` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lte_module.f90#L27)).

Intended initial shallow aquifer flow in mm. SWAT+ main (6f515368) reads it, but uses it only in calibration parameter handling and calibration output; it does not initialize the simulated HRU-lte shallow aquifer flow.
