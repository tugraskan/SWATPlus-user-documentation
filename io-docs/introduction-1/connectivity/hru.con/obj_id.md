---
description: ID of the receiving object
---

# obj\_id

**Code reference:** `ob(i)%obtypno_out(isp)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L370)).

The ID of the receiving object is a foreign key referencing the object ID ([id](id.md)) in the connect file of the receiving object.

SWAT+ [uses this number as the row position](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect.f90#L221-L276) of the receiver in its connect file, so [IDs](id.md) must run 1, 2, 3, ... in row order.
