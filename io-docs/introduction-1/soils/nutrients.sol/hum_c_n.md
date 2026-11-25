---
description: Humus C:N ratio
---

# hum\_c\_n

**Code reference:** `solt_db(isolt)%hum_c_n` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L19)).

Humus carbon-to-nitrogen ratio (`ratio`, typical range `8–12`; Fortran struct default: `10.0`) used to initialize nitrogen in the active and stable humus pools (kg/ha) in [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L136) and [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L142):

$$N_{\text{act},l} = \frac{C_{\text{act},l}}{R_{\text{CN}}}, \qquad N_{\text{sta},l} = \frac{C_{\text{sta},l}}{R_{\text{CN}}}$$

where $R_{\text{CN}}$ is `hum_c_n`, and $C_{\text{act},l}$ and $C_{\text{sta},l}$ are active and stable humus carbon (kg/ha). A positive value must be supplied because SWAT+ divides by `hum_c_n` without a zero-guard.
