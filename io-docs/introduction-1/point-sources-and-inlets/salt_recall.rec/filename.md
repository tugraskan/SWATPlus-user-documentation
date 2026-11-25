---
description: "Recall input filename"
---

# filename

**Code reference:** `rec_salt(i)%filename` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L233), [open](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_salt.f90#L114)).

Name (`character(len=30)`) of the input file supplying the salt recall time series when `typ /= 4`; see [`'salt_filename'.rec`](../salt_filename.rec/README.md). Note that `recall_read_salt` is not called in SWAT+ main (`6f515368`).
