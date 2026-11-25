---
description: "Fraction of each mineral in the cell"
---

# fract(m)

**Code reference:** `gwsol_minl_state(i)%fract(m)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L533), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1708)).

Fraction of the cell occupied by each salt mineral, one value per mineral, for an unstructured grid ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1705-L1709)). *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).* The mineral reaction routine is empty in this source.
