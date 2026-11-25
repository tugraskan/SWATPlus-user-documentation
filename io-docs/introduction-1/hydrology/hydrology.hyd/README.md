---
description: This file defines the hydrological characteristics of the HRUs
---

# hydrology.hyd

Each record supplies hydrologic parameters for an HRU. After the title and header, [`hydrol_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrol_read.f90#L27-L48) reads the fields positionally. Older files may label the `pet_co` column `harg_pet`.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Name of the hydrology record | string | n/a | n/a | n/a |
| [lat_ttime](lat_time.md) | Lateral flow travel time | real | days | 0 | 0-180 |
| [lat_sed](lat_sed.md) | Sediment concentration in lateral and tile flow | real | mg/L | 0 | 0-5000 |
| [can_max](can_max.md) | Maximum canopy storage | real | mm | 1 | 0-100 |
| [esco](esco.md) | Soil evaporation compensation factor | real | none | 0.5 | 0.01-1 |
| [epco](epco.md) | Plant uptake compensation factor | real | none | 0 | 0.01-1 |
| [orgn_enrich](orgn_enrich.md) | Organic nitrogen enrichment ratio for loading with sediment | real | none | 0 | 0-1 |
| [orgp_enrich](orgp_enrich.md) | Enrichment ratio for sediment-attached phosphorus | real | none | 0 | 0-1 |
| [cn3_swf](cn3_swf.md) | Soil water adjustment factor for CN3 | real | none |  | 0-1 |
| [bio_mix](bio_mix.md) | Biological mixing efficiency | real | none | 0.2 |  |
| [perco](perco.md) | Percolation coefficient | real | none |  | 0-1 |
| [lat_orgn](lat_orgn.md) | Organic nitrogen concentration in lateral flow | real | mg/L |  | 0-200 |
| [lat_orgp](lat_orgp.md) | Organic phosphorus concentration in lateral flow | real | mg/L |  | 0-200 |
| [pet_co](harg_pet.md) | Multiplier for daily potential evapotranspiration | real | none | 1 | 0.8-1.2 |
| [latq_co](cn_plntet.md) | Lateral flow coefficient | real | none |  | 0-1 |
