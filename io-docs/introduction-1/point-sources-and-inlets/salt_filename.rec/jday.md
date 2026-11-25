---
description: Julian day in a salt-ion recall file
---

# jday

**Code reference:** `jday` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L19), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L200)).

Integer Julian day (`1`–`366`). For daily records (`typ = 1` in [`salt_recall.rec`](../salt_recall.rec/README.md)), `jday` indexes the daily slot in `rec_salt(i)%hd_salt(istep, iyrs)`. Note that `recall_read_salt` is not called in SWAT+ main (`6f515368`).
