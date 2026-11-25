---
description: >-
  Fraction of maximum stomatal conductance corresponding to the second point on
  the stomatal conductance curve
---

# frac\_stcon

**Code reference:** `pldb(ic)%gmaxfr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L67)).

**Current use:** above 1 kPa, conductance is multiplied by `max(0.1, 1 − s × (deficit − 1))`, with slope `s` derived from this value and [vpd](vpd.md) ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L89), [`et_pot.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/et_pot.f90#L239-L245)).

The first point on the stomatal conductance curve is comprised of a vapor pressure deficit of 1 kPa and a fraction of maximum stomatal conductance equal to 1.00.

As with radiation-use efficiency, stomatal conductance is sensitive to vapor pressure deficit. Stockle et al. (1992) compiled a short list of stomatal conductance response to vapor pressure deficit for a few plant species. Due to the paucity of data, default values for the second point on the stomatal conductance vs. vapor pressure deficit curve are used for all plant species in the database.

{% hint style="info" %}
The fraction of maximum stomatal conductance (_frac\_stcon_) is set to 0.75 and the vapor pressure deficit corresponding to the fraction given by [vpd](vpd.md) is set to 4.00 kPa. If the user has actual data, they should use those values, otherwise the default values are adequate.
{% endhint %}

#### References

> Stockle et al. (1992)
