---
description: "Stored sediment"
---

# sed_stor

**Code reference:** `wet(j)%sed` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L33)).

Bulk sediment in the storage hydrograph after settling or flushing. The low-volume branch clears the stored mass before the controller checks for a flush. [Settling](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_sediment.f90#L17-L53), [Flushing](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wetland_control.f90#L227-L236)

**Unit:** tons.

See [sediment and particle sizes](README.md#sediment-and-particle-sizes) and [reporting periods](README.md#how-to-read-the-reporting-periods).

[Back to the output table](README.md).
