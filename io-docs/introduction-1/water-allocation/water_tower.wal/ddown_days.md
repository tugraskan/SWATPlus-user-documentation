---
description: "Number of days to draw down storage to zero"
---

# ddown_days

**Code reference:** `wtow(iwtow)%ddown_days` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L182), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_tower_read.f90#L43)).

Number of days to draw down water-tower storage to zero (`days`; uninitialized in the derived-type definition).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
