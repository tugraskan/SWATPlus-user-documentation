---
description: Name of the topography record
---

# name (topography.hyd)

**Code reference:** `topo_db(ith)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topography_data_module.f90#L6)).

Name of the topography record (up to 16 characters). Reference it from [hru-data.hru](../../hydrologic-response-units/hru-data.hru/topo.md) or [rout_unit.rtu](../../routing-units/untitled/topo.md). An unmatched HRU name is logged and selects the built-in topography record. [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L132-L139) · [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L25-L38) · [`ru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_read.f90#L233-L239)
