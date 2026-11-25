---
description: Grassed-waterway activation token
---

# flag

**Code reference:** `grwaterway_db(igrwwop)%grwat_i` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L49)).

This column is parsed from the input file, but [`structure_set_parms`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/structure_set_parms.f90#L73) unconditionally sets the HRU flag to 1 when the grassed-waterway record is applied. The user-supplied value is therefore ignored; the column serves as a positional placeholder in the file format.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but its value is overridden to 1 by `structure_set_parms` and is not used directly.)*
