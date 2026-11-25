---
description: "Cell number; not checked"
---

# cell_id

**Code reference:** `cell_id` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L161), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1672)).

Cell number. SWAT+ reads it but does not check it: the line's position decides which cell the values belong to ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1671-L1673)). Keep the lines in cell order. *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
