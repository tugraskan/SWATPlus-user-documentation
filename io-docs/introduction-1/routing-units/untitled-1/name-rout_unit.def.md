---
description: Name of the Routing Unit
---

# name (rout\_unit.def)

**Code reference:** `ru_def(iru)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L484), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L126)).

Name of the Routing Unit definition, read into `ru_def(iru)%name` when `elem_tot > 0` (or into `namedum` when `elem_tot <= 0` at [`ru_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L118)).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
