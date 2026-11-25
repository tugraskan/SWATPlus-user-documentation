---
description: Fraction of HRU that drains into wetland (read but not used by SWAT+ main (6f515368))
---

# hru\_frac

**Code reference:** `wet_hyddb(ires)%frac` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L93)).

SWAT+ main (6f515368) reads and stores hru_frac but does not use it in a calculation. Changing this value does not affect model results in this version.
