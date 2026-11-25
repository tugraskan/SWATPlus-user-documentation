---
description: "Default boundary type for boundary cells"
---

# bc_type

**Code reference:** `bc_type_int` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L159), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L241)).

Boundary type copied to every cell before [cells.gw](../cells.gw/bc_type_array_i.md) is read; that file's `bc_type` column can replace it cell by cell ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L321-L325)). It matters only for boundary cells (`stat` = 2).

* **2:** no flow. An active cell next to the boundary cell exchanges no water with it ([`gwflow_lateral.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L59-L62)).
* **Any other value, e.g. 1:** constant head. Darcy flow to and from the boundary cell is computed, and the boundary head is reset to its initial head each time step ([`gwflow_lateral.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_lateral.f90#L155-L157)).
