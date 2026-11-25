---
description: Calendar year to start printing output (for daily printing only)
---

# yrc\_start

**Code reference:** `pco%yrc_start` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L161)).

Calendar year (`year`; Fortran struct default: `0`) to start daily output printing. If set to `0`, [`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L779) sets `pco%yrc_start = time%yrc` (the starting year of the simulation).

In [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L195), `yrc_start` only controls `pco%day_print` (daily outputs) and does not affect monthly, yearly, or average-annual outputs.
