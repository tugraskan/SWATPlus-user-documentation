---
description: Pointer to the filter strip file
---

# vfs

**Code reference:** `lum(ilu)%fstrip` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_data_module.f90#L19), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L56)).

Character string (`len=40`, default `""`) acting as a foreign key referencing [name](../../structural-practices/filterstrip.str/name_fsdb.md) in [**filterstrip.str**](../../structural-practices/filterstrip.str/README.md), or `"null"` when no vegetative filter strip is simulated. Matched against `filtstrip_db%name` in [`landuse_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L115-L122) (unmatched non-`"null"` values are logged at [`#L161-L163`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L161-L163)) and assigned to `hru(iihru)%fstrip` in [`hru_lum_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lum_init.f90#L36).
