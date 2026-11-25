---
description: "Second date value; not used"
---

# year

**Code reference:** `dum` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L28)).

Second value of each daily line, normally the year. SWAT+ reads it into a placeholder and does not check it ([`gwflow_simulate.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_simulate.f90#L580)). *(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
