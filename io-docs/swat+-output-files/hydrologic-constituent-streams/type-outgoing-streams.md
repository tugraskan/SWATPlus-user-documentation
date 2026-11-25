---
description: "Object type code of the source object"
---

# type

**Code reference:** `ob(iob)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L336)).

Object type code of the source object.

Position 7 of the outgoing data prefix carries this value. Each row in the dormant writer represents one outgoing connection of the source object. [Data write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsout_output.f90#L22)

This field has no physical unit.

The pinned source has no active call to this report writer. See the [family status and layouts](README.md).
