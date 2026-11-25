---
description: "Curve-number diagnostic"
---

# cn

**Code reference:** `bwb_d%cn` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/output_landscape_module.f90#L18)).

Full HRUs calculate the curve number from soil water, with a frozen-soil adjustment. The wetland branch skips the surface routine and can retain an earlier value or the initialized zero. HRU-LTE calculates the curve number using its single soil-water store. [Calculation and reporting details](README.md#snow-irrigation-and-drainage)

This field has no physical unit in the output table.

[Back to the output table](README.md).
