---
description: Pointer to the overland Manning's n database
---

# ov\_mann

**Code reference:** `lum(ilu)%ovn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_data_module.f90#L16), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L56)).

Character string (`len=40`, default `""`) acting as a foreign key referencing [name](../ovn_table.lum/name_ovn.md) in [**ovn\_table.lum**](../ovn_table.lum/README.md). SWAT+ matches `lum(ilu)%ovn` against `overland_n%name` during initialization in [`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L385-L390) to set `hru(iihru)%luse%ovn`.
