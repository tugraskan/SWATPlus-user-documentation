---
description: Unique ID of the recall database record
---

# id (recall\_db.rec)

**Code reference:** `k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recalldb_read.f90#L16), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recalldb_read.f90#L46-L49)).

Leading integer identifier on each row of `recall_db.rec`. During parsing, [`recalldb_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recalldb_read.f90#L46) reads this integer into `i` to select `recall_db(i)`, then backspaces and re-reads it into local variable `k` ([`recalldb_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recalldb_read.f90#L48-L49)). After selecting the array slot `i`, `k` is not used further.
