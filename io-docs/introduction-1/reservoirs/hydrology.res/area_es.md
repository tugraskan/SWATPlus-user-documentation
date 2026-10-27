---
description: Reservoir surface area when reservoir is filled to emergency spillway
---

# area\_es

For SWAT+ to calculate the reservoir surface area each day, the surface area at two different water volumes must be defined. Variables referring to the principal spillway can be thought of as variables referring to the normal reservoir storage volume, while variables referring to the emergency spillway can be thought of as variables referring to the maximum reservoir storage volume.

By default, QSWAT+ will assume that the reservoir surface area at emergency spillway equals [area\_ps](area_ps.md) \* 1.15.

If area_es is zero or negative when SWAT+ reads hydrology.res, the model sets area_es to 1.5 times area_ps.
