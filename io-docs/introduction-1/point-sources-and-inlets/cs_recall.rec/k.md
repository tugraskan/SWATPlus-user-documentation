---
description: "Record number"
---

# k

**Code reference:** `k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L26), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L105-L108)).

Leading integer identifier on each row of `cs_recall.rec`. During parsing, [`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L105-L108) reads this integer into `i` to select `rec_cs(i)`, then backspaces and re-reads it into local variable `k`. Note that `recall_read_cs` is not called in SWAT+ main (`6f515368`).
