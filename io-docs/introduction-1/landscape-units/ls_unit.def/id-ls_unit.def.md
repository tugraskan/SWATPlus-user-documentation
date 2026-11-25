---
description: ID of the Landscape Unit
---

# id (ls\_unit.def)

**Code reference:** `k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L22), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L65)).

Sequential integer identifier of the Landscape Unit (`integer`, dimensionless, range `1..mlsu`, default `0`). SWAT+ reads `k` on each row ([`lsu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/lsu_read_elements.f90#L65-L70)) and indexes `lsu_out(i)` by file-row order `1..mlsu`.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
