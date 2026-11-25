---
description: "Incoming connection fraction"
---

# frac_in

**Code reference:** `ob(iob)%frac_in(iin)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrograph_module.f90#L380)).

Incoming connection fraction.

Position 12 of the incoming data prefix carries this value. Each row in the dormant writer represents one incoming connection of the receiving object. The routing code uses this fraction when it scales the upstream constituent record for its incoming diagnostic. [Data write](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hcsin_output.f90#L22) · [Incoming fraction applied](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/command.f90#L206)

**Unit:** fraction.

The pinned source has no active call to this report writer. See the [family status and layouts](README.md).
