---
description: "Number of regions"
---

# mreg

**Code reference:** `mreg` -> `db_mx%res_out` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_elements.f90#L19), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_elements.f90#L38), [stored](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_read_elements.f90#L74)).

Total number of reservoir cataloging units defined in [`res_catunit.def`](README.md) (`integer`, dimensionless, default `0`), stored in `db_mx%res_out`.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
