---
description: "Fractions by row and column"
---

# grid_val(i,j)

**Code reference:** `grid_val(i,j)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L41), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1701)).

For a structured grid with `read_type` = `array`, `n_rows` lines of `n_cols` fractions. The array they are read into is never allocated, and the values are not copied to the cells ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1699-L1702)). *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).* The mineral reaction routine is empty in this source.
