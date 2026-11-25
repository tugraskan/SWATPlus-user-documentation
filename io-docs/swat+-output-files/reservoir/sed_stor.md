---
description: "Sediment storage in the reservoir"
---

# sed_stor

**Code reference:** `res(j)%sed` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L33)).

Bulk sediment remaining in storage after the active release and settling calculations. On the branch that runs settling, the calculation deducts the estimated export before the water balance caps release. The later low-volume reset can clear the stored mass. [Settling](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_sediment.f90#L17-L51), [Water balance](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L159-L214)

**Unit:** tons.

Storage values are snapshots on the reporting date. See [sediment and particle sizes](README.md#sediment-and-particle-sizes).

[Back to the output table](README.md).
