---
description: "Precipitation volume"
---

# precip

**Code reference:** `wet_wat_d(j)%precip` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_body_module.f90#L9)).

Precipitation volume.

**Unit:** m3.

Daily precipitation volume is precipitation in mm multiplied by the full HRU area in ha and a factor of 10. It is calculated before the surface-area fraction is applied to the reported wetland area. [Precipitation calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L57)

See the [reporting periods](README.md#how-to-read-the-reporting-periods) for how the writer combines daily values.

[Back to the output table](README.md).
