---
description: Pointer to the pathogen initialization file for reservoirs
---

# path

**Code reference:** `res_init_dat_c(ires)%path` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_data_module.f90#L46)).

The pointer to the pathogen initialization file is a foreign key referencing [path\_init\_name\_ipathi](../../initialization/path_water.ini/path_init_name_ipathi.md) in [**path\_water.ini**](../../initialization/path_water.ini/).

For reservoirs, [`res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read.f90#L102-L103) resolves the matching record index and [`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L117-L121) initializes water-column and benthic pathogen concentrations. For wetlands, [`wet_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_initial.f90#L68-L69) resolves the index into `wet_init%path`, but does not apply it during wetland initialization.
