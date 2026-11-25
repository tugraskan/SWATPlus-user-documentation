---
description: "Sulfate exchanged by channel diversion (removal negative, addition positive)"
---

# so4_div

**Code reference:** `chsalt_d(iru)%salt(isalt)%div` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_salt_module.f90#L13)).

The header describes signed sulfate exchange with removal negative and addition positive. The active producer records the last qualifying daily Recall removal as a negative mass. Positive inputs enter the routed inlet. See [daily channel calculations](channel-salt.md#daily-channel-calculations).

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](channel-salt.md).
