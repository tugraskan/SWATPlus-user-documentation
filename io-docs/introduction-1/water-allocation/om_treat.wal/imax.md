---
description: "Number of records"
---

# imax

**Code reference:** `imax / db_mx%om_treat` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_treat_read.f90#L15), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_treat_read.f90#L34)).

Number of organic/mineral records in `om_treat.wal` (stored in `db_mx%om_treat`). Used to allocate `wtp_om_treat` and `om_treat_name` and to bound name-crosswalk searches.
