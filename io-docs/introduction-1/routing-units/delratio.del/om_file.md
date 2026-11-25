---
description: "Name of the organic/mineral delivery-ratio record in dr_om.del"
---

# om\_file

**Code reference:** `dr_db(ii)%om_file` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_module.f90#L18), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L47)).

Foreign key (16-character string) matching [dr\_om\_name](../dr_om.del/dr_om_name.md) in [**dr\_om.del**](../dr_om.del/) during [`dr_read_om.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_om.f90#L69-L76). If the name is unmatched, `dr_om_num(idr)` remains `0`, pointing to the zero-initialized `dr(0)` record.
