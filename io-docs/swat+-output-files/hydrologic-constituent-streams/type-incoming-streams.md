---
description: "Object type code of the receiving object"
---

# type

**Code reference:** `ob(iob)%typ` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L336)).

Object type code of the receiving object.

Position 7 of the incoming data prefix carries this value. Each row in the dormant writer represents one incoming connection of the receiving object. [Data write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsin_output.f90#L22)

This field has no physical unit.

The pinned source has no active call to this report writer. See the [family status and layouts](README.md).
