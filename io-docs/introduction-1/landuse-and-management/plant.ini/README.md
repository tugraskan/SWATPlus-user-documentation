---
description: This file stores information about the plants growing in a plant community.
---

# plant.ini

A plant community can consist of plants growing at the same time or plants growing in rotation.&#x20;

The structure of the file **plant.ini** is different than that of most other SWAT+ input files. The first line for each plant community specifies how many plants there are in the community and what the initial year of the rotation is. It is followed by one line per plant in the community.&#x20;

| Field                         | Description                                      |   Type  |   Unit   |  Default |    Range    |
| ----------------------------- | ------------------------------------------------ | :-----: | :------: | :------: | :---------: |
| [name](name_pcom.md)          | Plant community name                             |  string |    n/a   |    n/a   |     n/a     |
| [plnt\_cnt](plnt_cnt.md) | Number of plants in the community                | integer |    n/a   |          |             |
| [rot\_yr\_ini](rot_yr_ini.md) | Initial rotation year                            | integer |    n/a   |          |             |
| [plnt\_name](plnt_name.md) | Plant name as in plant database                  |  string |    n/a   |          |     n/a     |
| [lc\_status](lc_status.md) | Land cover status at start of simulation         |  string |    n/a   |          |     n/a     |
| [lai\_init](lai_init.md) | Initial Leaf Area Index                          |   real  |  m^2/m^2 |    0.0   |   0.0-8.0   |
| [bm\_init](bm_init.md) | Initial plant biomass                            |   real  |   kg/ha  |    0.0   |  0.0-1000.0 |
| [phu\_init](phu_init.md) | Initial fraction of plant heat units accumulated |   real  | fraction |    0.0   |  0.0-100.0  |
| [plnt\_pop](plnt_pop.md) | Plant population                                 |   real  |    n/a   |    0.0   |             |
| [yrs\_init](yrs_init.md) | Age of plant at start of simulation              |   real  |   years  |    0.0   |             |
| [rsd\_init](rsd_init.md) | Initial residue cover                            |   real  |   kg/ha  | 10000.00 | 0.0-10000.0 |
