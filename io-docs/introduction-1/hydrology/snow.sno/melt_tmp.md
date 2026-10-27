---
description: Snow melt base temperature
---

# melt\_tmp

SWAT+ considers snowmelt when the daily maximum air temperature exceeds `melt_tmp` and snow is present. The melt amount is calculated from the average of the estimated snowpack temperature and daily maximum air temperature, minus `melt_tmp`; negative melt is set to zero.
