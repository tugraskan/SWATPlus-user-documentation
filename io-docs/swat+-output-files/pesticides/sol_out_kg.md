---
description: "Dissolved and sorbed pesticide leaving"
---

# sol_out_kg

**Code reference:** `chpst_d(j)%pest(ipest)%sol_out` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_pesticide_module.f90#L12)).

For an SD channel, this is the dissolved fraction of the total outgoing pesticide load, using a fraction recalculated for that pesticide. The reservoir calculates dissolved export first from the water pesticide mass and removes it before calculating sorbed export. [Channel split](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L441-L457), [Reservoir release](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L172-L190).

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](channel-reservoir-pesticide-balance.md).
