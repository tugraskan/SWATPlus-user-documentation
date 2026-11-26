---
description: Switch for the optional last column of plants.plt and soil_plant.ini
---

# event

**Code reference:** `bsn_cc%nam1` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L24), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Controls whether optional trailing columns are read from [**plants.plt**](../../databases/plants.plt/) ([`plant_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_parm_read.f90#L232-L240), [`#L352-L360`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_parm_read.f90#L352-L360)) and [**soil\_plant.ini**](../../initialization/soil_plant.ini/) ([`soil_plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_plant_init.f90#L46-L53)). Despite its legacy `event` column name, this flag does not control sub-daily event routing in SWAT+ main (`6f515368`).

| Value | Effect |
| ----- | ------ |
| 0 (default) | The last column of **plants.plt** (description) is ignored, and **soil\_plant.ini** is read without a `cs` column |
| any other value | The last column of **plants.plt** is read as the plant class (`pl_class`), and **soil\_plant.ini** is read with a `cs` column |
