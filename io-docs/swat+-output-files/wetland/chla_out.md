---
description: "Outgoing chlorophyll a"
---

# chla_out

**Code reference:** `wet_out_d(j)%chla` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L38)).

Chlorophyll-a exported with wetland water release. When the phosphorus threshold is met, the active calculation sets chlorophyll-a mass to water volume times `1.e-6` kg/m³ and allocates a fraction to the release. [Nutrient block details](README.md#what-the-nutrient-blocks-include).

**Unit:** kg.

Monthly and yearly rows sum daily masses. The average-annual row divides the accumulated mass by the number of printed years.

[Back to the output table](README.md).
