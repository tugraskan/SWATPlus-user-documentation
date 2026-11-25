---
description: "Pesticide database record identifier in pest.com"
---

# ipestcom\_db

**Code reference:** `ipestcom_db` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L32), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read.f90#L225)).

Integer pesticide database identifier (`0` by default) read on its own row before each block of recall entries in `pest.com`.

*(Note: In SWAT+ main (6f515368), this column is parsed into memory but is not used in simulation calculations).*
