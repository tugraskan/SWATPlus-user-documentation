---
description: "Name of the pesticide delivery-ratio record in dr_pest.del"
---

# pest\_file

**Code reference:** `dr_db(ii)%pest_file` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_module.f90#L19), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L47)).

Foreign key (16-character string) matching [dr\_pest\_name(ii)](../dr_pest.del/dr_pest_name_ii.md) in [**dr\_pest.del**](../dr_pest.del/) during [`dr_read_pest.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_pest.f90#L72-L79). It is read and crosswalked only when `cs_db%num_pests > 0` in [`constituents.cs`](../../constituents/constituents.cs.md) ([`dr_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L57)), and is applied to standalone `dr` spatial objects in [`constit_hyd_mult.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_hyd_mult.f90#L19-L22) (not to Routing Unit elements).
