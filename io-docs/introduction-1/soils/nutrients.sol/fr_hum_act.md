---
description: Fraction of soil humus that is active
---

# fr\_hum\_act

**Code reference:** `solt_db(isolt)%fr_hum_act` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L18)).

Fraction of soil humus assigned to the active pool (`fraction`, `0–1`; Fortran struct default: `0.02`). If `fr_hum_act < 1e-9`, [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L129) replaces it with `0.02`. SWAT+ partitions each layer's total organic carbon $C_{\text{tot},l}$ (kg/ha) between active and stable humus in [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L135) and [`soil_nutcarb_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_init.f90#L141):

$$C_{\text{act},l} = f_{\text{act}} \cdot C_{\text{tot},l}, \qquad C_{\text{sta},l} = (1 - f_{\text{act}}) \cdot C_{\text{tot},l}$$

where $f_{\text{act}}$ is `fr_hum_act`.
