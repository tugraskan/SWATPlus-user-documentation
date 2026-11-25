---
description: Name of the watershed
---

# name

**Code reference:** `bsn%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L10)).

Name of the watershed (`character(len=25)`; Fortran struct default: `""`). SWAT+ reads this value as the first field of the `bsn` record in [`basin_read_objs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_read_objs.f90#L38) and echoes it to output file header banners and basin summary rows (for example, [`basin_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_output.f90#L72)).
