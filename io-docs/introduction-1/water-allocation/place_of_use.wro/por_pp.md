---
description: "POR record tag"
---

# pp (POR)

**Code reference:** `pp` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L17), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L104)).

5-character record tag (for example `por`) read into local variable `pp` at the start of each POR row ([`water_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_read.f90#L104)). Its value is not checked or stored.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
