---
description: "Final reported sediment yield per unit area"
---

# sedyld

**Code reference:** `bls_d%sedyld` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L152)).

The final full-HRU sediment yield divided by HRU area. The yield can include surface erosion, sediment routed across the HRU, wetland release, and sediment from lateral and tile water. Storage and conservation practices can change the value before the HRU writes it. [surface and runon](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L311-L338), [lateral and tile contribution](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/swr_latsed.f90#L32-L42), [routing and conservation adjustments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L590-L621), [per-area conversion](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L871-L877).

**Unit:** t/ha.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to the output table](README.md).
