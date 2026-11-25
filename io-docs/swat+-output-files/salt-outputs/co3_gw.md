---
description: "Carbonate entering the channel from groundwater"
---

# co3_gw

**Code reference:** `chsalt_d(iru)%salt(isalt)%gw_in` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_salt_module.f90#L9)).

Carbonate from groundwater in the saved linked-aquifer discharge, multiplied by the channel's share. Direct GWFlow exchanges update channel salt storage outside this diagnostic. See [daily channel calculations](channel-salt.md#daily-channel-calculations).

**Unit:** kg.

The same printed heading can appear in daily, monthly, yearly, and average-annual variants of this family. The reporting interval changes the row period; this page does not infer a total-versus-average rule beyond what the family output and source establish.

[Back to schema](channel-salt.md).
