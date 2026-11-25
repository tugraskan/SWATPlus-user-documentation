---
description: "Object ID in GIS"
---

# gis_id

**Code reference:** `ob(iob)%gis_id` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L355)).

Object ID in GIS.

This field has no physical unit in the output table.

For individual files, this is the reservoir object's GIS ID. Basin files write the literal placeholder `1`. [Individual writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/reservoir_output.f90#L19), [Basin writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_reservoir_output.f90#L38)

[Back to the output table](README.md).
