---
description: Name of the soil nutrient record
---

# name (nutrients.sol)

**Code reference:** `solt_db(isolt)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L14)).

The name of the soil nutrient record (Fortran struct default: `"default"`) is a primary key referenced by [nutrients](../../initialization/soil_plant.ini/nutrients.md) in [**soil\_plant.ini**](../../initialization/soil_plant.ini/) and matched during HRU initialization in [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L88).
