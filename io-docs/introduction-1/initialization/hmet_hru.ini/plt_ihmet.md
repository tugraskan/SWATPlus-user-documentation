---
description: "Amount of constituent on plant at start of simulation (read but not used in main 6f515368)"
---

# plt(ihmet)

**Code reference:** `hmet_soil_ini(ihmeti)%plt(ihmet)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L292)).

Intended initial heavy-metal amount on HRU plants, read in [`hmet_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hmet_hru_aqu_read.f90#L62). The loading loop (`ipest = 1, cs_db%num_metals`) indexes `plt(ihmet)` with `ihmet` left at `imax + 1` from the allocation loop ([`hmet_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hmet_hru_aqu_read.f90#L45-L64)), and `hmet_soil_ini%plt` is never read in any simulation calculation.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
