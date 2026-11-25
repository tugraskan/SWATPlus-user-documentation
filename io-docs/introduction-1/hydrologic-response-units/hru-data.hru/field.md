---
description: Pointer to the field file
---

# field

**Code reference:** `hru_db(i)%dbsc%field` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L167)).

The pointer to the field file is a foreign key referencing [name](../../hydrology/field.fld/name.md) in [**field.fld**](../../hydrology/field.fld/). [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L168-L176) matches the name, and [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L83-L86) copies the field length, width and angle to the HRU.

`null` selects no field record. A name that matches no record does the same and writes a "not found" warning.
