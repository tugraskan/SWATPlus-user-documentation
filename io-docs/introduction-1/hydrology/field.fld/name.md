---
description: Name of the field
---

# name (field.fld)

**Code reference:** `field_db(ith)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topography_data_module.f90#L16)).

Name of the field record (up to 16 characters). Reference it from [hru-data.hru](../../hydrologic-response-units/hru-data.hru/field.md) or [rout_unit.rtu](../../routing-units/untitled/field.md). An unmatched HRU name uses the built-in field record and is logged unless the name is `null`. The routing-unit reader copies the field properties on a match. [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L168-L176) · [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L83-L86) · [`ru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read.f90#L241-L250)
