---
description: Julian day to start printing output (for daily printing only)
---

# day\_start

**Code reference:** `pco%day_start` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L159)).

Julian day (`1–366`; Fortran struct default: `0`) to start daily output printing. If set to `0`, [`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L777) resets `pco%day_start = 1`.

In [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L195), `pco%day_print` becomes `"y"` once `time%day >= pco%day_start` and `time%yrc >= pco%yrc_start`. This setting only gates daily output printing, not monthly, yearly, or average-annual outputs.
