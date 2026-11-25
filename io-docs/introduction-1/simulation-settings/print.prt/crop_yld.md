---
description: Code for printing crop-yield output
---

# crop\_yld

**Code reference:** `pco%crop_yld` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L174)).

Character flag (`"a"` = average annual, `"y"` = yearly, `"b"` = both, `"n"` = no; Fortran struct default: `"a"`) read in [`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L42).

When `"a"` or `"b"`, SWAT+ opens `crop_yld_aa.txt` (and `crop_yld_aa.csv` if `csvout = "y"`) in [`output_landscape_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L1268-L1279) and writes HRU average-annual crop yields in [`hru_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_output.f90#L308-L319). When `"y"` or `"b"`, [`output_landscape_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_init.f90#L1253-L1265) opens `crop_yld_yr.txt` (and `.csv`) headers (no data rows are written to unit `4010`), while [`header_yield.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_yield.f90#L21-L30) and [`time_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/time_control.f90#L284-L300) open and write `basin_crop_yld_yr.txt` and `basin_crop_yld_aa.txt`.
