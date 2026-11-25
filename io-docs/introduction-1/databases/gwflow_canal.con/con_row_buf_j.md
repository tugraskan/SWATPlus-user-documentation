---
description: "Connection cell, length, and stage"
---

# con_row_buf(j)

**Code reference:** `con_row_buf(j)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L116)).

A repeated three-value group, one per connection: groundwater cell number, canal length in the cell (m), and water stage elevation (m) ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1340-L1343)). On a structured grid the cell number is translated to the internal cell number ([`gwflow_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_read.f90#L1344-L1346)). Groups whose cell number resolves to 0 or less are skipped.

For channel-connected canals, the canal bed is `stage − canal depth` and exchange follows Darcy's law with seepage area `length × canal width` ([`gwflow_canal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_canal.f90#L112-L126)).
