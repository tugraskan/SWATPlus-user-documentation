---
description: "Record name in exco_pest.exc linked to this export-coefficient set"
---

# pest\_file

**Code reference:** `exco_db(ii)%pest_file` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_module.f90#L19), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L47)).

Foreign key (`character(len=16)`) storing a **record name** (not a filename) that matches [exco\_pest\_name(ii)](../exco_pest.exc/exco_pest_name_ii.md) in [**exco\_pest.exc**](../exco_pest.exc/README.md) (or `"null"` when unused) during [`exco_read_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_pest.f90#L73-L85). Only evaluated when `cs_db%num_pests > 0` ([`exco_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L57)).
