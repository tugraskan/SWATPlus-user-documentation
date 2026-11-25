---
description: "Capacity selector for reservoir filling"
---

# file_pointer

**Code reference:** `dtbl_flo(i)%act(iac)%file_pointer` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L25)).

For `wallo_dmd` with `fill_res`, enter `pvol` or `evol` to choose the reservoir capacity. Other flow-control actions do not use this column; enter `null`. [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L209-L222)
