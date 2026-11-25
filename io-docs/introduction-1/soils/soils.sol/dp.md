---
description: Depth from the soil surface to the bottom of the soil layer
---

# dp

**Code reference:** `soildb(isol)%ly(j)%z` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L47)).

Cumulative depth from the soil surface to the bottom of soil layer $l$ (mm; Fortran struct default: `1500.`). Values must increase monotonically down the profile. During reading in [`soil_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_db_read.f90#L79-L81), if input layer 1 has `dp < 20` mm and either `nly == 1` or layer 2 has `dp > 20` mm, layer 1 depth is raised to `20` mm.

When `soil_lyr_depths.sol` is absent and input layer 1 has `dp > 19.5` mm, [`soils_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L71-L81) inserts a 10 mm surface layer (`d = 10` mm) above the input layers. Layer thickness $\Delta z_l$ (mm) is then computed in [`soil_phys_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_phys_init.f90#L143) as:

$$\Delta z_l = d_l - d_{l-1}$$

where $\Delta z_l$ is layer thickness (mm), $d_l$ is the bottom depth of layer $l$ (`dp`, mm), and $d_0$ is the soil surface depth (`0` mm). The deepest layer's bottom depth also overwrites `soil%zmx` in [`hydro_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydro_init.f90#L127).
