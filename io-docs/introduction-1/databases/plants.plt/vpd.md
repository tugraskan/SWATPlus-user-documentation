---
description: >-
  Vapor pressure deficit corresponding to the second point on the stomatal
  conductance curve
---

# vpd

**Code reference:** `pldb(ic)%vpdfr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plant_data_module.f90#L66)).

**Current use:** this value $v$ and [frac\_stcon](frac_stcon.md) $g$ give the slope of the conductance decline, $(1 - g) / (v - 1)$ ([`plantparm_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/plantparm_init.f90#L89)). Do not enter 1, which divides by zero.

The first point on the stomatal conductance curve is comprised of a vapor pressure deficit of 1 kPa and a fraction of maximum stomatal conductance equal to 1.00.

As with radiation-use efficiency, stomatal conductance is sensitive to vapor pressure deficit. Stockle et al. (1992) compiled a short list of stomatal conductance response to vapor pressure deficit for a few plant species. Due to the paucity of data, default values for the second point on the stomatal conductance vs. vapor pressure deficit curve are used for all plant species in the database.

{% hint style="info" %}
The fraction of maximum stomatal conductance ([frac\_stcon](frac_stcon.md)) is set to 0.75 and the vapor pressure deficit corresponding to the fraction given by _vpd_ is set to 4.00 kPa. If the user has actual data, they should use those values, otherwise the default values are adequate.
{% endhint %}

#### References

> Stockle et al. (1992)
