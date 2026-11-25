---
description: Application operation type (read but not used in main 6f515368)
---

# app\_typ

**Code reference:** `chemapp_db(ichemapp)%op_typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L100), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_chemapp.f90#L45)).

Character string (`len=40`, default `" "`) intended to specify the application method (such as `spread`, `spray`, `inject`, or `direct`).

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
