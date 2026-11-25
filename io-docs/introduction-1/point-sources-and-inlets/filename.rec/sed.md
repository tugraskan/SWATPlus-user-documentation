---
description: Sediment load in an organic/mineral recall file
---

# sed

**Code reference:** `recall(i)%hd%sed` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L33), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L158-L171)).

Total sediment load (`metric tons`; Fortran default: `0.`). Read into `recall(i)%hd` and routed to `ob(icmd)%hd(1)` during simulation in [`command.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L325-L344) (with subdaily inputs summed across steps in [`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L158-L160)).
