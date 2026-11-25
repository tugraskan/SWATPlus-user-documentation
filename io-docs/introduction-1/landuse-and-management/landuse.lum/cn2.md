---
description: Pointer to the Curve Number database
---

# cn2

**Code reference:** `lum(ilu)%cn_lu` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_data_module.f90#L10), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L56)).

Character string (`len=40`, default `""`) acting as a foreign key referencing [name](../cntable.lum/name_cn.md) in [**cntable.lum**](../cntable.lum/README.md), or `"null"` to omit lookup. Matched against `cn%name` in [`landuse_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L79-L86) (unmatched non-`"null"` values are logged at [`#L149-L151`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L149-L151)), copied to `hru(iihru)%luse%cn_lu` in [`hru_lum_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_lum_init.f90#L39), and used to select the HRU's initial curve number by soil hydrologic group in [`cn2_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cn2_init.f90#L21-L32).
