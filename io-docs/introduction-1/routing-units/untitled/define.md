---
description: Routing Unit definition name (read but not used by the model)
---

# define

**Code reference:** `ru(i)%dbsc%elem_def` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_module.f90#L12)).

SWAT+ reads the `define` value as the first component of `ru(i)%dbsc` in [`ru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read.f90#L230), but does not use it to select a Routing Unit definition. Instead, [`ru_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read_elements.f90#L115-L126) reads `rout_unit.def` sequentially and associates its records with Routing Units by row position.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
