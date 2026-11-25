---
description: "Outflow decision-table name"
---

# dtbl

**Code reference:** `canal(ic)%dtbl` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L195), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L44,L53)).

25-character name of a decision table for canal outflow (default: `""`). Checked in [`wallo_canal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_canal.f90#L55): when `"null"`, daily outflow uses [ddown_days](ddown_days.md); the non-null `else` branch ([`wallo_canal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_canal.f90#L58-L60)) is empty in `6f515368`, and no decision-table crosswalk is performed at read time ([`water_canal_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_canal_read.f90#L63)).
