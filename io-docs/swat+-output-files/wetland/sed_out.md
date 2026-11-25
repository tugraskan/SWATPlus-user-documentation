---
description: "Bulk sediment in the release after settling or flushing"
---

# sed_out

**Code reference:** `wet_out_d(j)%sed` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L33)).

Bulk sediment export from settling, or the replacement load calculated when a nearly dry wetland flushes. The wetland reports the flush mass once. The HRU sediment-yield calculation uses that mass twice. [Settling calculation](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_sediment.f90#L35-L58), [Flush and HRU sediment yield](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L227-L259)

**Unit:** tons.

See [sediment and particle sizes](README.md#sediment-and-particle-sizes) and [reporting periods](README.md#how-to-read-the-reporting-periods).

[Back to the output table](README.md).
