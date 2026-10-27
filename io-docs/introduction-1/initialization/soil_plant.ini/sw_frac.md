---
description: Not used; initial soil water is controlled by sw_init in parameters.bsn
---

# sw\_frac

**Code reference:** `sol_plt_ini(ii)%sw_frac`

**Declared type:** `soil_plant_initialize` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/soil_plant_init.f90#L50), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_module.f90#L130)).

This input is read from `soil_plant.ini` but is not used afterward. Initial soil water is controlled by `sw_init` in `parameters.bsn`; when `sw_init` is zero or negative, SWAT+ estimates the initial fraction from annual precipitation.
