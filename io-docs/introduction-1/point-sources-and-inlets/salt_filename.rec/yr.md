---
description: Calendar year in a salt-ion recall file
---

# yr

**Code reference:** `iyr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L18), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L156-L208)).

Four-digit integer calendar year (`iyr`). The reader uses `iyr` to set `rec_salt(i)%start_yr` ([`recall_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L177)), `rec_salt(i)%end_yr` ([`recall_read_salt.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L159)), and simulation-year indexing. Note that `recall_read_salt` is not called in SWAT+ main (`6f515368`).
