---
description: "Decision table name for maximum POR level"
---

# dtbl_max (POR)

**Code reference:** `pou(ipou)%por(ipor)%dtbl_max` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L42), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L106)).

25-character decision table name intended to cap return flows at the POR (default: `""`).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
