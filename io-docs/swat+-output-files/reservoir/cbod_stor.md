---
description: "Carbonaceous Biochemical Oxygen Demand storage in the reservoir"
---

# cbod_stor

**Code reference:** `res(j)%cbod` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L41)).

Carbonaceous biochemical oxygen demand mass in storage comes from initialization and incoming water. An allocation withdrawal can remove some of the mass, and a low-volume reset can clear the storage record. [Mass conversion](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L1285-L1306), [Allocation withdrawal](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L99-L109), [Low-volume reset](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_nutrient.f90#L33-L38)

**Unit:** kg.

Storage values are snapshots on the reporting date. See [oxygen and temperature values](README.md#oxygen-and-temperature-values).

[Back to the output table](README.md).
