---
description: "Number of groundwater cells"
---

# ncell

**Code reference:** `ncell` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L6), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L237)).

Number of groundwater cells. SWAT+ reads exactly this many rows from [cells.gw](../cells.gw/README.md) and [cellcon.gw](../cellcon.gw/README.md), and sizes every cell array with it ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L409-L434), [`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L504-L510)). Unstructured per-cell lists in other files (for example tile flags and `cell_sol.gw`) also have `ncell` rows.
