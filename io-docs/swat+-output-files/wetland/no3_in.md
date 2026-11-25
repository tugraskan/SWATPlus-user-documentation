---
description: "Incoming nitrate nitrogen"
---

# no3_in

**Code reference:** `wet_in_d(j)%no3` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L36)).

Routed nitrate in the daily inflow record. This can include linked-channel floodplain input and GWFlow nitrate. Irrigation nitrate is added directly to standing water and does not enter this column. [Nutrient block details](README.md#what-the-nutrient-blocks-include).

**Unit:** kg N.

Monthly and yearly rows sum daily masses. The average-annual row divides the accumulated mass by the number of printed years.

[Back to the output table](README.md).
