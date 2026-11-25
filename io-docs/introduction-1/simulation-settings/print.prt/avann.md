---
description: Code for printing average annual output
---

# avann

**Code reference:** `pco%<obj>%a` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L144)).

Character flag (`"y"` = yes, `"n"` = no; Fortran struct default: `"n"`) controlling average-annual output at the end of the simulation (averaged over `time%yrs_prt` after `nyskip` warm-up years).

Legacy carbon rows `hru_cb` and `hru_cb_vars` have no average-annual writer call in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L539-L558), though any non-`"n"` value on `hru_cb` triggers the legacy end-of-simulation soil snapshot ([`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L529-L537)).
