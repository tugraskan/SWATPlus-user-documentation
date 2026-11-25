---
description: Code for printing output in CSV format
---

# csvout

**Code reference:** `pco%csvout` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L166)).

Character flag (`"y"` = yes, `"n"` = no; Fortran struct default: `"n"`) read in [`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L36). When set to `"y"`, SWAT+ opens and writes comma-separated (`.csv`) copies alongside enabled `.txt` and `.out` output files (for example, [`output_landscape_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L43) and [`header_write.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_write.f90#L65)).
