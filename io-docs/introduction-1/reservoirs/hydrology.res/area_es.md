---
description: Reservoir surface area when reservoir is filled to emergency spillway
---

# area\_es

**Code reference:** `res_hyddb(ires)%esa`

**Declared type:** `reservoir_hyd_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_hyd.f90#L49), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L71)).

For SWAT+ to calculate the reservoir surface area each day, the surface area at two different water volumes must be defined. Variables referring to the principal spillway can be thought of as variables referring to the normal reservoir storage volume, while variables referring to the emergency spillway can be thought of as variables referring to the maximum reservoir storage volume.

By default, QSWAT+ will assume that the reservoir surface area at emergency spillway equals [area\_ps](area_ps.md) \* 1.15.

If area_es is zero or negative when SWAT+ reads hydrology.res, the model sets area_es to 1.5 times area_ps.
