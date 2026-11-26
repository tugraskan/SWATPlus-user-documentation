---
description: Electrical conductivity of the soil layer
---

# ec

**Code reference:** `soildb(isol)%ly(j)%ec` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L58)).

Electrical conductivity of the soil layer (`dS/m`; Fortran struct default: `0.0`), representing bulk soil salinity and ionic strength. The value is read in [`soil_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_db_read.f90#L71), copied to `soil%ly%ec` ([`soils_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soils_init.f90#L92)), modifiable during calibration ([`cal_parm_select.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_parm_select.f90#L338)), and echoed to soil-property snapshot outputs ([`soil_nutcarb_write.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_nutcarb_write.f90#L697)), but never enters simulation physics.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
