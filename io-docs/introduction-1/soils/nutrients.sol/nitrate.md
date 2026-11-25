---
description: Nitrate N in soil surface
---

# nitrate

**Code reference:** `solt_db(isolt)%nitrate` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L17)).

Initial nitrate-nitrogen concentration at the soil surface (`ppm`; Fortran struct default: `7.0`). During initialization in [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L54) and [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L60-L64), values $\le 10^{-9}$ are replaced with `7.0` ppm ([fallback](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L59-L62)), and SWAT+ initializes each layer's nitrate-N mass (kg/ha) as:

$$N_{\text{NO3},l} = C_{N,0} \cdot f_{\text{dep},l} \cdot \frac{\rho_{b,l} \cdot \Delta z_l}{100}$$

where $C_{N,0}$ is `nitrate` (ppm), $f_{\text{dep},l}$ is the depth attenuation factor, $\rho_{b,l}$ is layer bulk density ($\text{Mg/m}^3$), and $\Delta z_l$ is layer thickness (mm).
