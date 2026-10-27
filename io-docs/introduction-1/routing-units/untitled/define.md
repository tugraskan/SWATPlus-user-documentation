---
description: Routing Unit definition name (read but not used by the model)
---

# define

**Code reference:** `ru(i)%dbsc%elem_def` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/ru_module.f90#L12)).

SWAT+ main (6f515368) reads the `define` value but does not use it to select a Routing Unit definition. The model reads `rout_unit.def` independently and associates its records with Routing Units by row position.
