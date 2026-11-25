---
description: Code for printing output in Net-CDF format (not used)
---

# cdfout

**Code reference:** `pco%cdfout` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L171)).

Character flag (`"y"` = yes, `"n"` = no; Fortran struct default: `"n"`) intended to control NetCDF output, read in [`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L36).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
