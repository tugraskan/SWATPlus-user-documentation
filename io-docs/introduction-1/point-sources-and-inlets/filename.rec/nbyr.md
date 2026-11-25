---
description: Number of years header value on line 2 of an organic/mineral recall file
---

# nbyr

**Code reference:** `nbyr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L27), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L92)).

Integer read from line 2 of `'om_filename'.rec` representing the number of years in the file. In [`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L99-L109), `nbyr` is parsed into a local variable, while `recall(i)%hyd_flo` and `recall(i)%hd` are actually allocated using the simulation year count `time%nbyr`.
