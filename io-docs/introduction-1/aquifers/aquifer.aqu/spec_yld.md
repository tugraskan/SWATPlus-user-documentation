---
description: Specific yield of the aquifer
---

# spec\_yld

**Code reference:** `aqudb(i)%spyld` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aquifer_module.f90#L19)).

Specific yield (m³/m³) is the volume of water that drains by gravity divided by the total aquifer volume. It converts between aquifer storage and water-table position: it sets initial storage in [`aqu_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_initial.f90#L174) and the daily water-table depth in [`aqu_1d_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_1d_control.f90#L106) (see [dep\_bot](dep_bot.md) and [dep\_wt](dep_wt-1.md)).

Use a value greater than 0. With _spec\_yld_ = 0, initial storage is zero and the daily water-table calculation divides by zero.
