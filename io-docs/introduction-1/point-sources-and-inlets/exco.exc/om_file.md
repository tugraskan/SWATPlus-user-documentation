---
description: "Record name in exco_om.exc linked to this export-coefficient set"
---

# om\_file

**Code reference:** `exco_db(ii)%om_file` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_module.f90#L18), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_db_read.f90#L47)).

Foreign key (`character(len=16)`) storing a **record name** (not a filename) that matches [exco\_om\_name](../exco_om.exc/exco_om_name.md) in [**exco\_om.exc**](../exco_om.exc/README.md) during [`exco_read_om.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/exco_read_om.f90#L70-L71).
