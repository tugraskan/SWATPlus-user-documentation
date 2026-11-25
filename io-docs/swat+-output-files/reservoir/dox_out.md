---
description: "Dissolved oxygen slot, left at zero by the reservoir controller"
---

# dox_out

**Code reference:** `res_out_d(j)%dox` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L42)).

The reservoir controller leaves this outflow slot at its zero default. [Outflow initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L38-L42), [Nutrient export assignments](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_nutrient.f90#L99-L115)

**Unit:** kg.

Monthly and yearly records sum the daily loads. The average-annual record divides the accumulated loads by the number of printed years. See [oxygen and temperature values](README.md#oxygen-and-temperature-values).

[Back to the output table](README.md).
