---
description: Number of layers in the soil
---

# nly

**Code reference:** `soildb(isol)%s%nly` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L65)).

Integer count of soil horizons (unit: `none`; Fortran struct default: `1`) listed beneath the soil profile row in `soils.sol`. It controls how many layer rows [`soil_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_db_read.f90#L58-L71) allocates and reads for each soil entry.

During initialization, if `soil_lyr_depths.sol` is not used and the first input layer depth exceeds 19.5 mm, [`soils_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L71-L74) increments the simulated layer count (`sol%s%nly`) by 1 to insert a 10 mm surface layer. When `soil_lyr_depths.sol` is present, [`soils_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L199) replaces the layer count with the number of custom layers.
