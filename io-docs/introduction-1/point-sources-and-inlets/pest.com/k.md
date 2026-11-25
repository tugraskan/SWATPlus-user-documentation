---
description: "Record number in pest.com"
---

# k

**Code reference:** `k` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L28), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L229-L232)).

Leading integer identifier on each recall row in `pest.com`. [`recall_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L229-L232) reads this integer into `i` to select `rec_pest(i)`, then backspaces and re-reads it into local variable `k`.
