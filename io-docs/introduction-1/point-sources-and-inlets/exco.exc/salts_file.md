---
description: "Record name in exco_salt.exc linked to this export-coefficient set"
---

# salts\_file

**Code reference:** `exco_db(ii)%salts_file` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_module.f90#L22), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L47)).

Foreign key (`character(len=16)`) storing a **record name** (not a filename) that matches [exco\_salt\_name(ii)](../exco_salt.exc/exco_salt_name_ii.md) in [**exco\_salt.exc**](../exco_salt.exc/README.md) (or `"null"` when unused) during [`exco_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_salt.f90#L74-L85). Only evaluated when `cs_db%num_salts > 0` ([`exco_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L60)).
