---
description: "Sand outflow slot, left at zero by the wetland controller"
---

# san_out

**Code reference:** `wet_out_d(j)%san` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L43)).

The wetland controller initializes the sand outflow slot to zero and leaves it at zero through settling and flushing. Bulk sediment export is available separately in [sed_out](sed_out.md). [Outflow initialization](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L59-L64), [Bulk sediment calculations](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_sediment.f90#L17-L61)

**Unit:** tons.

See [sediment and particle sizes](README.md#sediment-and-particle-sizes) and [reporting periods](README.md#how-to-read-the-reporting-periods).

[Back to the output table](README.md).
