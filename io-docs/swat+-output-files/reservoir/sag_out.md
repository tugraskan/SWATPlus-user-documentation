---
description: "Small aggregates outflow slot, left at zero by the reservoir controller"
---

# sag_out

**Code reference:** `res_out_d(j)%sag` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L46)).

The reservoir controller leaves this outflow slot at its zero default. The settling routine calculates only bulk sediment export, reported separately in [sed_out](sed_out.md). [Outflow initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L38-L42), [Settling and export](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_sediment.f90#L35-L58)

**Unit:** tons.

Monthly and yearly records sum the daily loads. The average-annual record divides the accumulated loads by the number of printed years. See [sediment and particle sizes](README.md#sediment-and-particle-sizes).

[Back to the output table](README.md).
