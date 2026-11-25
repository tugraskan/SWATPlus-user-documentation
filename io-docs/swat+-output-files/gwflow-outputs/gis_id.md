---
description: "Configured cell GIS identifier"
---

# gis_id

**Code reference:** `cell_gis_id(i)` ([cell writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_output.f90#L1225)).

The writer sets local `gis_id = cell_gis_id(i)`, then prints it. This identifier can differ from the cell index in `unit`.

This is an identifier or label, with no physical unit.

[Back to the cell water-balance schema](cell-water-balance.md).
