---
description: "Number of regions"
---

# mreg

**Code reference:** `mreg` -> `db_mx%aqu_out`, `db_mx%aqu_reg` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L19), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L39), [stored](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L81)).

Total number of aquifer cataloging-unit regions defined in [`aqu_catunit.def`](README.md) (`integer`, dimensionless, default `0`). In [`aqu_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_read_elements.f90#L39-L124), `mreg` is stored into `db_mx%aqu_out` (`#L81`) and `db_mx%aqu_reg` (`#L124`).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
