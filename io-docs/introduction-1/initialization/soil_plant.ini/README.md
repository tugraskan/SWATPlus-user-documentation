---
description: >-
  This file references several other files, which initialize nutrients and
  constituents in soils.
---

# soil\_plant.ini

[`soil_plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_plant_init.f90#L21-L56) reads `soil_plant.ini` (listed as `soil_plant_ini` on the `init` row of [**file.cio**](../../master-file-file.cio.md)), and [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L80-L128) matches each record's pointers against the constituent initialization tables for every HRU. The trailing `cs` column is read only when [event](../../basin-1/codes.bsn/event.md) (`bsn_cc%nam1`) in [**codes.bsn**](../../basin-1/codes.bsn/) is nonzero ([`soil_plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/soil_plant_init.f90#L46-L52)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name-soil_plant.ini.md) | Name of the soil and plant initialization | string |  |  |  |
| [sw\_frac](sw_frac.md) | Intended initial soil-water fraction (read but not applied; `sw_init` in `parameters.bsn` controls initial water) | real |  |  |  |
| [nutrients](nutrients.md) | Pointer to the nutrient initialization file | string |  |  |  |
| [pest](pest.md) | Pointer to the pesticide initialization file | string |  |  |  |
| [path](path.md) | Pointer to the pathogen initialization file | string |  |  |  |
| [salt](salt.md) | Pointer to the salt initialization file | string |  |  |  |
| [hmet](hmet.md) | Intended pointer to the heavy-metal initialization file (read and crosswalked, but not used in simulation) | string |  |  |  |
| [cs](cs.md) | Pointer to the constituent soil initialization in `cs_hru.ini`; read only when `event` in `codes.bsn` is nonzero | string |  |  |  |

{% hint style="warning" %}
In SWAT+ main (`6f515368`), heavy-metal (`hmet`) initialization is parsed and crosswalked into memory but never used in simulation calculations, whereas pathogen (`path`) initialization is active in HRU surface-soil routines ([`pathogen_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pathogen_init.f90#L72-L83), [`path_ls_process.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_process.f90#L35), [`path_ls_runoff.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_runoff.f90#L22), and [`path_ls_swrouting.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_ls_swrouting.f90#L21)).
{% endhint %}
