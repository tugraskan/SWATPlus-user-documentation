---
description: "Precipitation on the reservoir surface"
---

# precip

**Code reference:** `res_wat_d(j)%precip` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_body_module.f90#L9)).

Precipitation on the reservoir surface.

**Unit:** m3.

Daily precipitation volume uses weather precipitation in mm times the surface area in ha and a factor of 10. The controller uses the area available before the end-of-day update. Monthly and yearly values are totals, and average annual divides the yearly totals by the number of printed years. Basin values aggregate the corresponding reservoir records. [Daily calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L168), [Period handling](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_output.f90#L31)

[Back to the output table](README.md).
