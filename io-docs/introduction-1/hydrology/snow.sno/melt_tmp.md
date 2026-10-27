---
description: Snow melt base temperature
---

# melt\_tmp

**Code reference:** `snodb(isno)%melttmp`

**Declared type:** `snow_parameters` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/snowdb_read.f90#L48), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hru_module.f90#L75)).

SWAT+ considers snowmelt when the daily maximum air temperature exceeds `melt_tmp` and snow is present. The melt amount is calculated from the average of the estimated snowpack temperature and daily maximum air temperature, minus `melt_tmp`; negative melt is set to zero.
