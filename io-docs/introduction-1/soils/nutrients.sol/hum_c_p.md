---
description: Humus C:P ratio
---

# hum\_c\_p

**Code reference:** `solt_db(isolt)%hum_c_p` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L20)).

Humus carbon-to-phosphorus ratio (`ratio`, typical range `70–90`; Fortran struct default: `80.0`) used to initialize phosphorus in the active and stable humus pools (kg/ha) in [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L137) and [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L143):

$$P_{\text{act},l} = \frac{C_{\text{act},l}}{R_{\text{CP}}}, \qquad P_{\text{sta},l} = \frac{C_{\text{sta},l}}{R_{\text{CP}}}$$

where $R_{\text{CP}}$ is `hum_c_p`, and $C_{\text{act},l}$ and $C_{\text{sta},l}$ are active and stable humus carbon (kg/ha). A positive value must be supplied because SWAT+ divides by `hum_c_p` without a zero-guard.
