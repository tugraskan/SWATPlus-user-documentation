---
description: "Source or receiving-object record number"
---

# k

**Code reference:** `k` / `mallo(imro)%src(i)%num` / `mallo(imro)%trn(i)%num` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L20), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L63-L67), [`#L90-L94`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L90-L94)).

Leading integer index (`1..src_obs` or `1..trn_obs`) on each source or receiving-object row. In [`manure_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L63-L67), [`#L90-L94`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L90-L94), the reader first reads this integer into `i` to index `src(i)` or `trn(i)` and record `%num = i`, then backspaces and reads `k` along with the rest of the row.
