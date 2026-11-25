---
description: This file stores information about the plants growing in a plant community.
---

# plant.ini

This file stores initial conditions for plants growing in a plant community, read by [`readpcom.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/readpcom.f90#L36-L71). A plant community can consist of plants growing simultaneously or in rotation.

The structure of **plant.ini** differs from most other SWAT+ input files: each community begins with a header row specifying the community name, number of plants (`plnt_cnt`), and initial rotation year (`rot_yr_ini`), followed by one row per plant in the community.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name_pcom.md) | Plant community name | string | n/a | n/a | n/a |
| [plnt\_cnt](plnt_cnt.md) | Number of plants in the community | integer | n/a | 1 |  |
| [rot\_yr\_ini](rot_yr_ini.md) | Initial rotation year | integer | n/a | 1 |  |
| [plnt\_name](plnt_name.md) | Plant name as in plant database | string | n/a | n/a | n/a |
| [lc\_status](lc_status.md) | Land cover status at start of simulation | string | n/a | n/a | n/a |
| [lai\_init](lai_init.md) | Initial Leaf Area Index | real | m^2/m^2 | 0.0 | 0.0-8.0 |
| [bm\_init](bm_init.md) | Initial plant biomass | real | kg/ha | 0.0 | 0.0-1000.0 |
| [phu\_init](phu_init.md) | Initial fraction of plant heat units accumulated | real | fraction | 0.0 | 0.0-100.0 |
| [plnt\_pop](plnt_pop.md) | Plant population (read but not used in main 6f515368) | real | n/a | 0.0 |  |
| [yrs\_init](yrs_init.md) | Fraction of years to maturity completed (despite legacy `yrs_init` label) | real | fraction | 0.0 |  |
| [rsd\_init](rsd_init.md) | Initial residue cover | real | kg/ha | 10000.00 | 0.0-10000.0 |
