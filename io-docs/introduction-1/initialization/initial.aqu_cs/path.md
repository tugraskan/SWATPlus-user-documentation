---
description: "Name of the referenced pathogen initialization record"
---

# path

**Code reference:** `aqu_init_dat_c_cs(iaqu)%path` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L89)).

Foreign key matched against [path\_init\_name(ipathi)](../path_water.ini/path_init_name_ipathi.md) in [**path\_water.ini**](../path_water.ini/) when `cs_db%num_paths > 0` ([`aqu_read_init_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init_cs.f90#L101)). After finding index `ics`, [`aqu_read_init_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_init_cs.f90#L104) copies `path_soil_ini(ics)%soil(ipath)` (from [**path\_hru.ini**](../path_hru.ini/)) into `cs_aqu(iaq)%path(ipath)`, though `cs_aqu%path` is never subsequently read in simulation calculations.
