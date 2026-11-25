---
description: Name of the land use and management record
---

# name (landuse.lum)

**Code reference:** `lum(ilu)%name` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_data_module.f90#L6), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L56)).

Unique character string (`len=40`, default `""`) identifying the land use and management record. This name is a primary key referenced by [lu\_mgt](../../hydrologic-response-units/hru-data.hru/lu_mgt.md) in [**hru-data.hru**](../../hydrologic-response-units/hru-data.hru/README.md). All names in `landuse.lum` must be unique.
