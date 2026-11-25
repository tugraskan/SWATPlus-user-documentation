---
description: Plant community name
---

# name (plant.ini)

**Code reference:** `pcomdb(icom)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L138), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readpcom.f90#L62)).

Character string (`len=40`, struct default `"frsd_frsd"`) identifying the plant community. This primary key is referenced by [plnt\_com](../landuse.lum/plnt_com.md) in [**landuse.lum**](../landuse.lum/README.md) ([`landuse_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L63)) and by `pcom` operations in `management.sch` ([`read_mgtops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/read_mgtops.f90#L45)). All names in `plant.ini` must be unique.
