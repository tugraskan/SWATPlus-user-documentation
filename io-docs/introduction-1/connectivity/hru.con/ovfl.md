---
description: Intended overbank-flooding pointer (printed in connectivity output)
---

# ovfl

**Code reference:** `ob(i)%props2` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L350)).

Intended overbank-flooding pointer. This HRU connectivity value does not control HRU flooding calculations in SWAT+ main (6f515368), but it is printed as `props2` in connectivity output when `hydcon` is enabled. For chandeg.con, the value is [copied to a variable](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L376) that no calculation reads.

**Current use:** [connectivity output](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hyd_connect_out.f90#L19).
