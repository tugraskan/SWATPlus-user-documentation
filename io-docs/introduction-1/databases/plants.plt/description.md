---
description: Description of the plant
---

# description

**Code reference:** `pldb(ic)%desc` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L98)); plant class `pl_class(ic)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L6)).

Last standard column: 55 without carbon, 58 with `carbon = 2`. Free-text description, up to 45 characters; it is read as a single list-directed value, so quote it if it contains spaces or commas.

When [event](../../basin-1/codes.bsn/event.md) in codes.bsn is not 0, SWAT+ reads one more column after the description as the plant class, up to 25 characters, which calibration conditions can match ([`plant_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_parm_read.f90#L232-L240), [`cal_conditions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cal_conditions.f90#L90)).
