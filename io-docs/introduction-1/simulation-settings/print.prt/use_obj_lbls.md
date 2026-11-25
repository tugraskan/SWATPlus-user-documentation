---
description: Controls whether print object rows are identified by label or fixed order
---

# use_obj_lbls

**Code reference:** `pco%use_obj_labels` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_module.f90#L168)).

When `use_obj_lbls` is `"n"` (Fortran struct default), [`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L49) reads the object rows in the fixed positional order expected by the reader and ignores the first-column label. For any other value, [`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L169-L771) matches each row by the object label in the first column (which is required for per-family/LSU carbon rows and GWFlow rows) and halts with `error stop` on an unrecognized label ([`basin_print_codes_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_print_codes_read.f90#L762-L768)). This field does not control database-format output.
