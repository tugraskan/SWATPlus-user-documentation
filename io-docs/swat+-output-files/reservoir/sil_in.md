---
description: "Silt entering the reservoir"
---

# sil_in

**Code reference:** `res_in_d(j)%sil` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L44)).

Silt measured as mass in the routed incoming hydrograph for an operating reservoir. Water delivered directly by allocation enters storage through a separate record. [Inflow and storage](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_control.f90#L38-L63), [Reported inflow](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L252-L263), [Allocation delivery](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_pou_deliv.f90#L104-L112)

**Unit:** tons.

Monthly and yearly records sum the daily loads. The average-annual record divides the accumulated loads by the number of printed years. See [sediment and particle sizes](README.md#sediment-and-particle-sizes).

[Back to the output table](README.md).
