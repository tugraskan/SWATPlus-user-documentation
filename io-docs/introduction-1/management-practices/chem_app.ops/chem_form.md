---
description: Chemical form (read but not used in main 6f515368)
---

# chem\_form

**Code reference:** `chemapp_db(ichemapp)%form` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_operations_module.f90#L99), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_chemapp.f90#L45)).

Character string (`len=40`, default `" "`) intended to identify the physical form of the applied chemical (such as `solid` or `liquid`).

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
