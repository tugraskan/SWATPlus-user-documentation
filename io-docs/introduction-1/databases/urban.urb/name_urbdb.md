---
description: Name of the urban land type
---

# name (urban.urb)

**Code reference:** `urbdb(iu)%urbnm` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/urban_data_module.f90#L6)).

The name holds up to 16 characters and is matched against `urb_lu` in landuse.lum ([`plant_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_init.f90#L377-L382)). A name that matches no record leaves the HRU without urban processes, with no warning.

The name of the urban land type is a primary key referenced by [urban](../../landuse-and-management/landuse.lum/urb_ro.md) in [**landuse.lum**](../../landuse-and-management/landuse.lum/). All names in the **urban.urb** database must be unique.

The names in the urban database are also used by QSWAT+ to link the grid codes in land use/land cover maps to SWAT+ urban land types.

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
