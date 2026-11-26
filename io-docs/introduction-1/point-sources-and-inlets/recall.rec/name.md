---
description: User label for the recall input
---

# name

**Code reference:** `recall(i)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L427), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L80)).

User-assigned label (`character(len=25)`) identifying the recall entry in `recall.rec`.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
