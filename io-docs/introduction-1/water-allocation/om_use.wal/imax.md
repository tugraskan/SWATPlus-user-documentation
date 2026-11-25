---
description: "Number of records"
---

# imax

**Code reference:** `imax / db_mx%om_use` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_use_read.f90#L15), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_use_read.f90#L34)).

Number of organic/mineral records in `om_use.wal` (stored in `db_mx%om_use`). Used to allocate `wuse_om_efflu` and `om_use_name` and to bound name-crosswalk searches.
