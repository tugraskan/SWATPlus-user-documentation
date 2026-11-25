---
description: "Amount of constituent in soil at start of simulation (read but not used in main 6f515368)"
---

# soil(ihmet)

**Code reference:** `hmet_soil_ini(ihmeti)%soil(ihmet)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L291)).

Intended initial heavy-metal amount in HRU soil, read in [`hmet_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hmet_hru_aqu_read.f90#L60). The loading loop (`ipest = 1, cs_db%num_metals`) indexes `soil(ihmet)` with `ihmet` left at `imax + 1` from the allocation loop ([`hmet_hru_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hmet_hru_aqu_read.f90#L45-L64)), and `hmet_soil_ini%soil` is never read in any simulation calculation.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
