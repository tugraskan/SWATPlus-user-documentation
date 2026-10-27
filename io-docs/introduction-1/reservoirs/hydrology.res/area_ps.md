---
description: Reservoir surface area when reservoir is filled to principal spillway
---

# area\_ps

For SWAT+ to calculate the reservoir surface area each day, the surface area at two different water volumes must be defined. Variables referring to the principal spillway can be thought of as variables referring to the normal reservoir storage volume, while variables referring to the emergency spillway can be thought of as variables referring to the maximum reservoir storage volume.

If a shapefile is used to implement reservoirs in QSWAT+, the interface will assume that the reservoir surface area at principal spillway equals the area of the polygon.   &#x20;

If area_ps is zero or negative when SWAT+ reads hydrology.res, the model sets area_ps to 0.08 times vol_ps.
