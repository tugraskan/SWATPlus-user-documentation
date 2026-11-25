---
description: "Outgoing nitrate nitrogen"
---

# no3_out

**Code reference:** `wet_out_d(j)%no3` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L36)).

Nitrate exported with wetland water release after nutrient settling. The routine skips the nitrate export calculation when the remaining wetland volume falls below `1.e-6` m³, even if the release has a positive water volume. [Nutrient block details](README.md#what-the-nutrient-blocks-include).

**Unit:** kg N.

Monthly and yearly rows sum daily masses. The average-annual row divides the accumulated mass by the number of printed years.

[Back to the output table](README.md).
