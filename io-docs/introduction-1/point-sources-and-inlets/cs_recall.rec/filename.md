---
description: "Name of the input file supplying constituent recall values"
---

# filename

**Code reference:** `rec_cs(i)%filename` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L245), [open](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L113)).

Name (`character(len=30)`) of the input file supplying general-constituent recall values when `typ /= 4`; see [`'cst_filename'.rec`](../cst_filename.rec/README.md). Note that `recall_read_cs` is not called in SWAT+ main (`6f515368`).
