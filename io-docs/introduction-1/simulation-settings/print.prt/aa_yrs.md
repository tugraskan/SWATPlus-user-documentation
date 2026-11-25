---
description: End years for average annual print intervals (not read on SWAT+ dev)
---

# aa\_yrs

**Code reference:** none on SWAT+ dev.

End years of the average-annual print intervals, entered after [aa\_int\_cnt](aa_int_cnt.md) on line five. SWAT+ dev reads only the first value of that line and ignores the rest, so these years have no effect ([`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L32)).
