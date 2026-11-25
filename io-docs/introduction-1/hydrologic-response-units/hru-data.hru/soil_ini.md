---
description: Pointer to the soil and plant initialization file
---

# soil\_plant\_init

**Code reference:** `hru_db(i)%dbsc%soil_plant_init` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L164)).

The pointer to the soil and plant initialization file is a foreign key referencing [name](../../initialization/soil_plant.ini/name-soil_plant.ini.md) in [**soil\_plant.ini**](../../initialization/soil_plant.ini/). [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L80-L84) matches the name and then resolves the nutrient and constituent records listed in that entry.

If the name matches no record, the HRU silently keeps the first record in soil_plant.ini: the index starts at 1, so the "not found" check for 0 never triggers ([`hru_module.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L146-L156)). Check the spelling of this name.
