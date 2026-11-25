---
description: Calendar month in a salt-ion recall file
---

# mo

**Code reference:** `mo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L20), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L200)).

Integer calendar month (`1`–`12`). For monthly records (`typ = 2` in [`salt_recall.rec`](../salt_recall.rec/README.md)), `mo` indexes the monthly slot in `rec_salt(i)%hd_salt(istep, iyrs)`. Note that `recall_read_salt` is not called in SWAT+ main (`6f515368`).
