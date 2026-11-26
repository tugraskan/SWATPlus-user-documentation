---
description: "Annual maximum POR inflow"
---

# ann_max (POR)

**Code reference:** `pou(ipou)%por(ipor)%ann_max` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L44), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L106)).

Annual maximum inflow limit at the POR (`m^3/s`; default: `0.`).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
