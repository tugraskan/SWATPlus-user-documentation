---
description: "Tile flags by row and column"
---

# grid_int(i,j)

**Code reference:** `grid_int(i,j)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L40), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1065)).

Tile flags for a structured grid: `n_rows` lines of `n_cols` values ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1063-L1073)). In this source the row-by-column arrays used here are never allocated, so this layout cannot be read. Use the per-cell [tile](tile.md) layout. This is listed in `MODEL_ISSUES.md`.
