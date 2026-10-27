---
description: Sediment settling velocity input (read but not used by the model)
---

# stl\_vel

SWAT+ main (6f515368) reads and stores `stl_vel`, but the value is not used in the reservoir or wetland sediment calculation. The model's active settling calculation uses a coefficient computed from `d50`; it does not compute or use this settling-velocity input.
