---
description: "Evaporation from the reservoir surface"
---

# evap

**Code reference:** `res_wat_d(j)%evap` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_body_module.f90#L10)).

Evaporation from the reservoir surface.

**Unit:** m3.

Daily evaporation uses PET, the reservoir evaporation coefficient, and the surface area available before the end-of-day update. The controller limits the reported loss to the water available at that step. Monthly and yearly values are totals, and average annual divides the yearly totals by the number of printed years. [Daily calculation and limit](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_control.f90#L168), [Period handling](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_output.f90#L31)

[Back to the output table](README.md).
