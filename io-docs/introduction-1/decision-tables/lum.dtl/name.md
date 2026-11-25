---
description: User-defined action name (written to management diagnostics)
---

# name

**Code reference:** `dtbl_lum(i)%act(iac)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/conditional_module.f90#L20)).

The action name is defined by the user. SWAT+ main (6f515368) writes it to management diagnostics when management output is enabled; it is not the action-type selector.

**Current use:** [management diagnostic output](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L163).

The name can also affect behavior. The reader matches `days_act` limit strings to this column, `puddle` looks it up as a tillage name, and irrigation branches test for the exact name `ponding`. [`dtbl_lum_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/dtbl_lum_read.f90#L298-L303) · [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L127-L134)
