---
description: Texture of the soil
---

# texture

**Code reference:** `soildb(isol)%s%texture` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L70)).

Profile-level soil texture label (`character(len=16)`). It is not used in soil physics calculations, but the column must not be left blank because list-directed reading in [`soil_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_db_read.f90#L65) expects a token. The value is stored in `soil%texture` and can be used as a filter condition during calibration ([`cal_conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L77)).
