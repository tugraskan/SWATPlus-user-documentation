---
description: Name of the hydrology record
---

# name (hydrology.hyd)

**Code reference:** `hyd_db(ithyd)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hydrology_data_module.f90#L7)).

Name of the hydrology record (up to 16 characters), as referenced by [hydro](../../hydrologic-response-units/hru-data.hru/hydro.md) in `hru-data.hru`. An unmatched name leaves the HRU on the built-in record. The warning identifies the file as `hydrograph.hyd`. [`hru_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_read.f90#L141-L148) · [`topohyd_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/topohyd_init.f90#L25-L36)
