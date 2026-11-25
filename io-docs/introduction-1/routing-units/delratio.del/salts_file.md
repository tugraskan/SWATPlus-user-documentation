---
description: "Name of the salt-ion delivery-ratio record in dr_salt.del"
---

# salts\_file

**Code reference:** `dr_db(ii)%salts_file` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_module.f90#L22), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L47)).

Foreign key (16-character string) matching [dr\_salt\_name(ii)](../dr_salt.del/dr_salt_name_ii.md) in [**dr\_salt.del**](../dr_salt.del/) during [`dr_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_read_salt.f90#L72-L79). It is read and crosswalked only when `cs_db%num_salts > 0` in [`constituents.cs`](../../constituents/constituents.cs.md) ([`dr_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L60)), and is applied to standalone `dr` spatial objects in [`constit_hyd_mult.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_hyd_mult.f90#L34-L37) (not to Routing Unit elements).
