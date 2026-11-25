---
description: "One fraction for all cells"
---

# single_value

**Code reference:** `single_value` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L178), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1697)).

For a structured grid with `read_type` = `single`, one fraction for the whole grid. It is assigned only to a row-by-column array that is never allocated or copied to the cells ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1696-L1698)). *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).* The mineral reaction routine is empty in this source.
