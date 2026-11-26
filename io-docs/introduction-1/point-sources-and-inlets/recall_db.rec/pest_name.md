---
description: Pesticide constituent name in recall_db.rec
---

# pest\_name

**Code reference:** `recall_db(i)%pest` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_module.f90#L8), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recalldb_read.f90#L49)).

Pesticide constituent-group name (`character(len=25)`) associated with this recall database record.

*(Note: In SWAT+ main (6f515368) and dev (aa4179fe), this column is parsed into memory but is not used in simulation calculations).*
