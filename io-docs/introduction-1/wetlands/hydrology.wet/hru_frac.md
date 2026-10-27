---
description: Fraction of HRU that drains into wetland (read but not used by SWAT+ main (6f515368))
---

# hru\_frac

**Code reference:** `wet_hyddb(ires)%frac`

**Declared type:** `wetland_hyd_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wet_read_hyd.f90#L57), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L93)).

SWAT+ main (6f515368) reads and stores hru_frac but does not use it in a calculation. Changing this value does not affect model results in this version.
