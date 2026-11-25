---
description: "Bulk sediment export calculated before the water-release cap"
---

# sed_out

**Code reference:** `res_out_d(j)%sed` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L33)).

Bulk sediment release calculated by the decision-table branch when the stored concentration exceeds the equilibrium threshold. The sediment load uses the smoothed water release before the water balance caps it. The alternate release branch leaves the load at zero. [Release paths](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_control.f90#L121-L175), [Sediment calculation](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_sediment.f90#L17-L58)

**Unit:** tons.

Monthly and yearly records sum the daily loads. The average-annual record divides the accumulated loads by the number of printed years. See [sediment and particle sizes](README.md#sediment-and-particle-sizes).

[Back to the output table](README.md).
