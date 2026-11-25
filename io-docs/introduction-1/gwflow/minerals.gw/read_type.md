---
description: "single or array"
---

# read_type

**Code reference:** `read_type` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L46), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1695)).

For a structured grid, how the mineral's values are given: `single` for one value, `array` for `n_rows` lines of `n_cols` values ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1695-L1703)). *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).* The mineral reaction routine is empty in this source.
