---
description: "Number of salt minerals"
---

# gw_nminl

**Code reference:** `gw_nminl` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_module.f90#L507), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1683)).

Number of salt minerals: the number of fractions on each cell line, or the number of mineral blocks in the structured layout ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1683-L1688)). *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).* The mineral reaction routine is empty in this source.
