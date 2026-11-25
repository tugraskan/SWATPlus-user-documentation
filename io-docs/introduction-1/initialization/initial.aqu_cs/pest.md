---
description: "Name of the referenced pesticide initialization record"
---

# pest

**Code reference:** `aqu_init_dat_c_cs(iaqu)%pest` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L88)).

Foreign key referencing [name](../pest_water.ini/name.md) (`pest_init_name`) in [**pest\_water.ini**](../pest_water.ini/). When `cs_db%num_pests > 0`, [`aqu_read_init_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init_cs.f90#L81-L95) matches this name and initializes `cs_aqu(iaq)%pest(ipest)` from `pest_water_ini(ics)%water(ipest)` ([`aqu_read_init_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init_cs.f90#L89)).
