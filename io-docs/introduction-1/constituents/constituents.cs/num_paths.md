---
description: "Number of pathogens to simulate"
---

# num\_paths

**Code reference:** `cs_db%num_paths` ([`declaration`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L18), [`read`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_db_read.f90#L42-L45)).

Number of pathogens carried in the simulation. The default is 0, which turns pathogen simulation off. It sets how many names are read from the [paths](paths.md) line and how many pathogen values other input files must supply. HRU pathogen processes run only when it is above 0 ([`hru_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L583-L587)).
