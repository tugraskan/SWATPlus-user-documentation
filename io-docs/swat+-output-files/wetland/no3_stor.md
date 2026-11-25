---
description: "Stored nitrate nitrogen"
---

# no3_stor

**Code reference:** `wet(j)%no3` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L36)).

Nitrate left in standing water after the applicable inflow additions, soil seepage, settling, and outflow export. Each reporting period writes the current stored mass. [Nutrient block details](README.md#what-the-nutrient-blocks-include).

**Unit:** kg N.

The writer uses the current storage in each of the four periods.

[Back to the output table](README.md).
