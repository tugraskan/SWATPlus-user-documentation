---
description: "Salt lost through channel seepage"
---

# mg_seep

**Code reference:** `chsalt_d(iru)%salt(isalt)%seep` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_salt_module.f90#L11)).

Magnesium lost from the working inlet through seepage in the channel router. The field can retain an earlier value when the inlet is too small for a new calculation. See [daily channel calculations](channel-salt.md#daily-channel-calculations).

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](channel-salt.md).
