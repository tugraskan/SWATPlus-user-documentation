---
description: Julian day to stop printing output (for daily printing only)
---

# day\_end

**Code reference:** `pco%day_end` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L160)).

Julian day (`1–366`; Fortran struct default: `0`) to stop daily output printing. If set to `0`, [`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L778) resets `pco%day_end = 366`.

In [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L199-L201), once `time%day > pco%day_end` and `time%yrc == pco%yrc_end`, SWAT+ sets `pco%day_print = "n"` and `pco%day_print_over = "y"` for the remainder of the simulation.
