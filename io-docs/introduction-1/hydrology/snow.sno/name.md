---
description: Name of the snow record
---

# name (snow.sno)

**Code reference:** `snodb(isno)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_module.f90#L73)).

Name of the snow record (up to 40 characters), as referenced by [snow](../../hydrologic-response-units/hru-data.hru/snow.md) in `hru-data.hru`. The HRU uses the built-in record if the name is unmatched. SWAT+ logs an unmatched name unless it is `null`. [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L159-L166) · [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L48-L52)
