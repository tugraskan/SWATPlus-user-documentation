---
description: "Name of the object or SWAT+ setup (basin outputs)"
---

# name

**Code reference:** `ob(iob)%name` ([individual writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/recall_output.f90#L23); [basin writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/basin_recall_output.f90#L23)).

Name of the object or SWAT+ setup (basin outputs).

This identifier has no physical unit.

Individual recall records write six identifying values. Basin records write five: `jday`, `mon`, `day`, `yr`, and the basin `name`, followed directly by the hydrograph. The [family warning](README.md) documents CSV-specific shifts.

[Back to the Individual Recall schema](individual-recall.md); [Basin Recall schema](basin-recall.md).
