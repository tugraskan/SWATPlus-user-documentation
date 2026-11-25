---
description: "Internal object table index of the source object"
---

# iob

**Code reference:** `iob` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsout_output.f90#L14)).

Internal object table index of the source object.

Position 5 of the outgoing data prefix carries this value. Each row in the dormant writer represents one outgoing connection of the source object. [Data write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsout_output.f90#L22)

This field has no physical unit.

The pinned source has no active call to this report writer. See the [family status and layouts](README.md).
