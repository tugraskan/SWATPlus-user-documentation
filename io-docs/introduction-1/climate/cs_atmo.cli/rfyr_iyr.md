---
description: "Yearly precipitation concentration in mg/L"
---

# rfyr(iyr)

**Code reference:** `atmodep_cs(iadep)%cs(ics)%rfyr(iyr)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L228)).

Concentration in rainfall in mg/L for the indicated period. The model applies $0.01CP$ in kg/ha each day, where $C$ is the current period concentration and $P$ is daily precipitation in mm. See [cs_rain.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_rain.f90#L42-L82).
