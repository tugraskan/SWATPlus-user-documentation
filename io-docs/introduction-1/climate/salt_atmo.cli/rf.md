---
description: "The annual average concentration of the salt ion in rainfall"
---

# rf

**Code reference:** `atmodep_salt(iadep)%salt(isalt)%rf` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/climate_module.f90#L224)).

Concentration in rainfall in mg/L for the indicated period. The model applies $0.01CP$ in kg/ha each day, where $C$ is the current period concentration and $P$ is daily precipitation in mm. See [salt_rain.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_rain.f90#L42-L82).
