---
description: "Zone label; not read"
---

# zone_id

**Code reference:** `split_fields(1)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L185)).

Label at the start of each zone line. SWAT+ does not read it: the zone number is the line's position in the file ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L394-L400)). Keep the labels equal to the line numbers (1, 2, 3, …) so the file reads the way the model uses it.
