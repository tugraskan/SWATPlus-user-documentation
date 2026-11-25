---
description: "Cell index"
---

# unit

**Code reference:** `i` ([cell writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1225)).

The cell water-balance writer prints the GWFlow cell index. Only cells with `gw_state(i)%stat == 1` receive these rows; this is not the basin placeholder 1.

This is an identifier or label, with no physical unit.

[Back to the cell water-balance schema](cell-water-balance.md).
