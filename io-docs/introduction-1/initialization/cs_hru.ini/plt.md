---
description: "Amount of constituent on plant at start of simulation (read but not used in main 6f515368)"
---

# plt

**Code reference:** `cs_soil_ini(ics)%plt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L292)).

Array of `2 * cs_db%num_cs` values allocated and read in [`cs_hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_hru_read.f90#L52-L72). It is never read in [`cs_hru_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_hru_init.f90#L44-L72) or any simulation routine.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
