---
description: Sediment settling velocity input (read but not used by the model)
---

# stl\_vel

**Code reference:** `res_sed(ires)%velsetlr` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L105)).

SWAT+ main (6f515368) reads and stores `stl_vel`, but the value is not used in the reservoir or wetland sediment calculation. The model's active settling calculation uses a coefficient computed from `d50`; it does not compute or use this settling-velocity input.
