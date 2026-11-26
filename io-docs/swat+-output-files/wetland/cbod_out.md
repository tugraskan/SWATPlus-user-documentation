---
description: "Carbonaceous biochemical oxygen demand slot, left at zero by the wetland controller"
---

# cbod_out

**Code reference:** `wet_out_d(j)%cbod` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L41)).

The wetland starts its carbonaceous biochemical oxygen demand outflow slot at zero and leaves it at zero. [Outflow initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L59-L64), [Export assignments](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L119-L137)

**Unit:** kg.

Monthly and yearly rows sum daily masses. The average-annual row divides the accumulated mass by the number of printed years.

[Back to the output table](README.md).
