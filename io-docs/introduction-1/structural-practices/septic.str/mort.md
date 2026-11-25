---
description: Mortality rate coefficient
---

# mort

**Code reference:** `sep(isep)%mrt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L40)).

Daily bacterial mortality rate coefficient in the biozone (dimensionless; [`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L211)):

$$R_{\text{mort}} = c_T \cdot k_m \cdot B$$

where $R_{\text{mort}}$ is daily mortality (kg/ha), $k_m$ is `mort` (dimensionless), $B$ is live biomass (kg/ha), and $c_T$ is the temperature factor (`1.0` in SWAT+ main (`6f515368`)). Dead biomass transfers to the biozone plaque pool.
