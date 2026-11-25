---
description: "Name of the heavy-metal delivery-ratio record in dr_hmet.del"
---

# hmet\_file

**Code reference:** `dr_db(ii)%hmet_file` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_module.f90#L21), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L47)).

Foreign key (16-character string) matching [dr\_hmet\_name(ii)](../dr_hmet.del/dr_hmet_name_ii.md) in [**dr\_hmet.del**](../dr_hmet.del/) during [`dr_read_hmet.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_hmet.f90#L73-L80). It is read and crosswalked only when `cs_db%num_metals > 0` in [`constituents.cs`](../../constituents/constituents.cs.md) ([`dr_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L59)), and is applied to standalone `dr` spatial objects in [`constit_hyd_mult.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_hyd_mult.f90#L29-L32) (not to Routing Unit elements).
