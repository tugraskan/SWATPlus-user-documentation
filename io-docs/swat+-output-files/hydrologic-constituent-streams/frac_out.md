---
description: "Outgoing connection fraction"
---

# frac_out

**Code reference:** `ob(iob)%frac_out(iiout)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L374)).

Outgoing connection fraction.

Position 12 of the outgoing data prefix carries this value. Each row in the dormant writer represents one outgoing connection of the source object. The outgoing writer emits this fraction alongside a shared `hcs1` value and leaves the shared value unscaled. [Data write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsout_output.f90#L22)

**Unit:** fraction.

The pinned source has no active call to this report writer. See the [family status and layouts](README.md).
