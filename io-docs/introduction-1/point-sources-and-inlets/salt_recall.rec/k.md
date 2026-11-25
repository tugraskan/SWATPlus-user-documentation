---
description: "Record number"
---

# k

**Code reference:** `k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L25), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L106-L109)).

Leading integer identifier on each row of `salt_recall.rec`. During parsing, [`recall_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L106-L109) reads this integer into `i` to select `rec_salt(i)`, then backspaces and re-reads it into local variable `k`. Note that `recall_read_salt` is not called in SWAT+ main (`6f515368`).
