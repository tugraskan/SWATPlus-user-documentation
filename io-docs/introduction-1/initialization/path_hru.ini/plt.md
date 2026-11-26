---
description: "Initial plant-compartment value for each pathogen (read but not used in main 6f515368)"
---

# plt

**Code reference:** `path_soil_ini(ipathi)%plt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L292)).

Intended initial pathogen level on plants (`#cfu/m^2` per the generic constituent-type declaration), read in [`path_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/path_hru_aqu_read.f90#L58) and copied into `hpath_bal(ihru)%path(ipath)%plant` in [`pathogen_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pathogen_init.f90#L83). `hpath_bal%path%plant` is never subsequently read in simulation calculations.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
