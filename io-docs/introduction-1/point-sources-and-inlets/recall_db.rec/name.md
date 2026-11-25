---
description: Name of the recall database record
---

# name

**Code reference:** `recall_db(i)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_module.f90#L6), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recalldb_read.f90#L49)).

Name (`character(len=13)`) of the recall database record. A reservoir decision-table action can reference this value through its `file_pointer` field ([`dtbl_res_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_res_read.f90#L92)).
