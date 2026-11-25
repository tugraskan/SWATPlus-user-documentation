---
description: Pointer to the septic file
---

# sep

**Code reference:** `lum(ilu)%septic` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_data_module.f90#L18), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L56)).

Character string (`len=40`, default `""`) acting as a foreign key referencing [name](../../structural-practices/septic.str/name_sepdb.md) in [**septic.str**](../../structural-practices/septic.str/README.md), or `"null"` when septic systems are not simulated. Matched against `sep%name` in [`landuse_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L106-L113) (unmatched non-`"null"` values are logged at [`#L158-L160`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L158-L160)) and assigned to `hru(iihru)%septic` in [`hru_lum_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lum_init.f90#L35).
