---
description: "Group label; not read"
---

# group_id

**Code reference:** `split_fields(1)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L185)).

Group label at the start of each line. SWAT+ does not read it; groups are numbered by line order ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L2328-L2331)). *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
