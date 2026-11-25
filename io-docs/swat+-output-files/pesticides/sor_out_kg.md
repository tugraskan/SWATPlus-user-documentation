---
description: "Dissolved and sorbed pesticide leaving"
---

# sor_out_kg

**Code reference:** `chpst_d(j)%pest(ipest)%sor_out` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_pesticide_module.f90#L13)).

For an SD channel, this is the sorbed fraction of the same total load used for the dissolved column. The reservoir calculates the sorbed amount from water pesticide mass remaining after dissolved export has been subtracted. [Channel split](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L441-L457), [Sequential reservoir removal](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_pest.f90#L172-L190).

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](channel-reservoir-pesticide-balance.md).
