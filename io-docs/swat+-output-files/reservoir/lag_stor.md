---
description: "Large aggregate storage in the reservoir"
---

# lag_stor

**Code reference:** `res(j)%lag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L47)).

Large aggregates in the storage hydrograph. The sediment routine clears all six stored size classes when bulk sediment concentration exceeds the equilibrium threshold. A low-volume reset also clears these fields. [Sediment calculation](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_sediment.f90#L17-L51), [Low-volume reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L33-L38)

**Unit:** tons.

Storage values are snapshots on the reporting date. See [sediment and particle sizes](README.md#sediment-and-particle-sizes).

[Back to the output table](README.md).
