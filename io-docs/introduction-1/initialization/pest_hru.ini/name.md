---
description: Record name
---

# name

**Code reference:** `pest_soil_ini(ipesti)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L290)).

Name of the HRU pesticide initialization set, read in [`pest_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_hru_aqu_read.f90#L57). It is matched against [pest](../soil_plant.ini/pest.md) in [**soil\_plant.ini**](../soil_plant.ini/) during HRU setup in [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L95-L96).
