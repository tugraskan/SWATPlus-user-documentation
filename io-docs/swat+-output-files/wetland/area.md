---
description: "Wetland surface area"
---

# area

**Code reference:** `wet_wat_d(j)%area_ha` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_body_module.f90#L8)).

Wetland surface area.

**Unit:** ha.

The daily record starts with the full HRU area. With positive stored volume, the controller applies a surface-area fraction for ordinary wetlands. Paddy areas retain the full HRU area. Yearly output sums monthly mean areas without dividing by 12. Average annual divides those yearly values by the number of printed years. [Area assignment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L58), [Surface-area fraction](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L82), [Reporting calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_output.f90#L37)

[Back to the output table](README.md).
