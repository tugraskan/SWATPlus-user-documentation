---
description: Calendar month in a general-constituent recall file
---

# mo

**Code reference:** `mo` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L21), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_read_cs.f90#L199)).

Integer calendar month (`1`–`12`). For monthly records (`typ = 2` in [`cs_recall.rec`](../cs_recall.rec/README.md)), `mo` indexes the monthly slot in `rec_cs(i)%hd_cs(istep, iyrs)`. Note that `recall_read_cs` is not called in SWAT+ main (`6f515368`).
