---
description: Pointer to the land use and management file
---

# lu\_mgt

**Code reference:** `hru_db(i)%dbsc%land_use_mgt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L163)).

The pointer to the land use and management file is a foreign key referencing [name](../../landuse-and-management/landuse.lum/name.md) in [**landuse.lum**](../../landuse-and-management/landuse.lum/) ([`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L70-L77)).

If the name matches no record, the HRU silently keeps the first record in landuse.lum: the index starts at 1, so the "not found" check for 0 never triggers ([`hru_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L146-L156)). Check the spelling of this name.
