---
description: Intended initial plant salt values (read but not used in main 6f515368)
---

# plt

**Code reference:** `salt_soil_ini(isalti)%plt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L292)).

Array of `cs_db%num_salts + 5` values allocated and read in [`salt_hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_hru_read.f90#L51-L71). It is never read in [`salt_hru_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_hru_init.f90#L44-L69) or any simulation routine.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
