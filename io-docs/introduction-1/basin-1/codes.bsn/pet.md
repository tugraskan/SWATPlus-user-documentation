---
description: Potential evapotranspiration (PET) method
---

# pet

**Code reference:** `bsn_cc%pet` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L20), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L24)).

Selects the method used to obtain daily potential evapotranspiration in [`et_pot.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/et_pot.f90#L115-L278) (struct default `0`). When `pet = 3`, [`basin_read_cc.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_cc.f90#L30-L40) opens `pet.cli` and SWAT+ uses imported daily PET values linked through [pet](../../climate/weather-sta.cli/pet.md) in [**weather-sta.cli**](../../climate/weather-sta.cli/) and [**pet.cli**](../../climate/pet.cli/).

| Code | Option |
| ---- | ------ |
| 0 | Priestley-Taylor method |
| 1 | Penman-Monteith method |
| 2 | Hargreaves method |
| 3 | Read daily PET values from **pet.cli** |
