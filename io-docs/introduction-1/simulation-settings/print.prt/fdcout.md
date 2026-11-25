---
description: Code for printing flow duration curve output
---

# fdcout

**Code reference:** `pco%fdcout` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L177)).

Character flag (`"y"` = yes, `"n"` = no; Fortran struct default: `"n"`) read in [`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L42).

Although the Fortran declaration comment reads `NOT ACTIVE`, when `fdcout = "y"`, [`header_write.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_write.f90#L15-L20) opens `flow_duration_curve.out`, [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L413-L419) accumulates daily flow duration curves and the Richards-Baker flashiness index for SWAT-DEG (`chandeg`) channels, and [`flow_dur_curve.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/flow_dur_curve.f90#L135-L146) writes the median annual duration curves and flashiness index.
