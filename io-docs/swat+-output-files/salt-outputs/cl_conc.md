---
description: "Salt concentration in channel outflow"
---

# cl_conc

**Code reference:** `chsalt_d(iru)%salt(isalt)%conc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_salt_module.f90#L15)).

This heading reports salt concentration in the channel outflow. The model divides the outgoing salt mass by outgoing water volume and converts to g/m3. [Daily calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_channel_control3.f90#L474)

**Unit:** g/m3.

See [reporting periods](channel-salt.md#reporting-periods) for how daily concentrations are combined.

[Back to schema](channel-salt.md).
