---
description: "Initial benthic-compartment value for each pathogen (not used in simulation in main 6f515368)"
---

# benthic

**Code reference:** `path_water_ini(ipathi)%benthic` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L334)).

Initial benthic-compartment value for each pathogen, read in [`path_cha_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_cha_res_read.f90#L63) and copied directly into `res_benthic(ires)%path(ipath)` ([`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L120)) and `ch_benthic(ich)%path(ipath)` ([`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L280)). Neither `res_benthic%path` nor `ch_benthic%path` is subsequently read in simulation calculations.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
