---
description: Name of the urban land type
---

# name (urban.urb)

**Code reference:** `urbdb(iu)%urbnm`

**Declared type:** `urban_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/urban_parm_read.f90#L42), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/urban_data_module.f90#L6)).

The name of the urban land type is a primary key referenced by [urban](../../landuse-and-management/landuse.lum/urb_ro.md) in [**landuse.lum**](../../landuse-and-management/landuse.lum/). All names in the **urban.urb** database must be unique.

The names in the urban database are also used by QSWAT+ to link the grid codes in land use/land cover maps to SWAT+ urban land types.&#x20;

| Name | Description                   |
| ---- | ----------------------------- |
| urhd | Residential - high density    |
| urmd | Residential - medium density  |
| urml | Residential - med/low density |
| urld | Residential - low density     |
| ucom | Commercial                    |
| uidu | Industrial                    |
| utrn | Transportation                |
| uins | Institutional                 |
| urbn | Generic                       |
