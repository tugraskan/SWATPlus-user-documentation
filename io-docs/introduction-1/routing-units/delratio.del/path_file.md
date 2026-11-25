---
description: "Name of the pathogen delivery-ratio record in dr_path.del"
---

# path\_file

**Code reference:** `dr_db(ii)%path_file` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_module.f90#L20), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L47)).

Foreign key (16-character string) matching [dr\_path\_name(ii)](../dr_path.del/dr_path_name_ii.md) in [**dr\_path.del**](../dr_path.del/) during [`dr_path_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_path_read.f90#L72-L79). It is read and crosswalked only when `cs_db%num_paths > 0` in [`constituents.cs`](../../constituents/constituents.cs.md) ([`dr_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dr_db_read.f90#L58)), and is applied to standalone `dr` spatial objects in [`constit_hyd_mult.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constit_hyd_mult.f90#L24-L27) (not to Routing Unit elements).
