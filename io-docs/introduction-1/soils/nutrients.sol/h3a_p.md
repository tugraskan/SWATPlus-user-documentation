---
description: H3A extractable P in soil surface (not used)
---

# h3a\_p

**Code reference:** `solt_db(isolt)%h3a_p` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_data_module.f90#L23)).

Initial Haney, Haney, Hossner, and Arnold (H3A) extractable phosphorus concentration in the soil surface (`ppm`; Fortran struct default: `0.25`). This field is read from `nutrients.sol` by [`solt_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/solt_db_read.f90#L47) as part of the full `solt_db` record.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
