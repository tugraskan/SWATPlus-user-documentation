---
description: "Repeated numeric temperature slots printed as null"
---

# null

The literal heading `null` appears three times, at the end of the storage, inflow, and outflow blocks. The writer supplies `wet(j)%temp`, `wet_in_d(j)%temp`, and `wet_out_d(j)%temp` respectively for daily output, with the matching period accumulators for inflow and outflow at longer intervals.

**Code reference:** compare the [header declarations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L568) and [record writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_output.f90#L20).

The printed unit is blank. The numeric component is declared in degrees Celsius. Storage and inflow values are inherited or mixed from input hydrographs. The controller leaves the outflow temperature at zero. [Oxygen and temperature values](README.md#oxygen-and-temperature-values)

[Back to the output table](README.md).
