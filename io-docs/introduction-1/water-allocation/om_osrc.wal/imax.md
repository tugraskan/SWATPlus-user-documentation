---
description: "Number of records"
---

# imax

**Code reference:** `imax / db_mx%om_src` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_osrc_read.f90#L15), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_osrc_read.f90#L34)).

Number of organic/mineral records in `om_osrc.wal` (stored in `db_mx%om_src`). Used to allocate `osrc_om` and `om_osrc_name` and to bound name-crosswalk searches.
