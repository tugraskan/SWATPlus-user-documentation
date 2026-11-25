---
description: Calendar year in a general-constituent recall file
---

# yr

**Code reference:** `iyr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L19), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L155-L207)).

Four-digit integer calendar year (`iyr`). The reader uses `iyr` to set `rec_cs(i)%start_yr` ([`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L176)), `rec_cs(i)%end_yr` ([`recall_read_cs.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L158)), and simulation-year indexing. Note that `recall_read_cs` is not called in SWAT+ main (`6f515368`).
