---
description: "Stored carbonaceous biochemical oxygen demand"
---

# cbod_stor

**Code reference:** `wet(j)%cbod` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L41)).

Carbonaceous biochemical oxygen demand mass in the storage hydrograph comes from initialization and inflow. A low remaining water volume can clear it. [Initialization conversion](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1285-L1306), [Low-volume reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_sediment.f90#L17-L24)

**Unit:** kg.

See [oxygen and temperature values](README.md#oxygen-and-temperature-values) and [reporting periods](README.md#how-to-read-the-reporting-periods).

[Back to the output table](README.md).
