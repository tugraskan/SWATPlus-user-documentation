---
description: "Solute name; not checked"
---

# name

**Code reference:** `name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L49), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1657)).

Solute name, for readability. SWAT+ reads it and discards it; lines are matched to solutes by position ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1656-L1658)). Solutes are always in this order: nitrate (`no3`), phosphorus (`p`), then the salt ions and the other constituents named in `constituents.cs`, in that file's order ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1609-L1639)). Write the names in that order. *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
