---
description: "Evaporation volume"
---

# evap

**Code reference:** `wet_wat_d(j)%evap` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_body_module.f90#L10)).

Evaporation volume.

**Unit:** m3.

The actual evapotranspiration routine removes water from wetland or paddy storage to meet the remaining evaporation demand, up to the available volume. It converts the removed depth to m3 using the full HRU area. [Evaporation calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/et_act.f90#L183)

See the [reporting periods](README.md#how-to-read-the-reporting-periods) for how the writer combines daily values.

[Back to the output table](README.md).
