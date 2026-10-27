---
description: >-
  Vapor pressure deficit corresponding to the second point on the stomatal
  conductance curve
---

# vpd

**Code reference:** `pldb(ic)%vpdfr` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L71)).

The first point on the stomatal conductance curve is comprised of a vapor pressure deficit of 1 kPa and a fraction of maximum stomatal conductance equal to 1.00.

As with radiation-use efficiency, stomatal conductance is sensitive to vapor pressure deficit. Stockle et al. (1992) compiled a short list of stomatal conductance response to vapor pressure deficit for a few plant species. Due to the paucity of data, default values for the second point on the stomatal conductance vs. vapor pressure deficit curve are used for all plant species in the database.&#x20;

{% hint style="info" %}
The fraction of maximum stomatal conductance ([frac\_stcon](frac_stcon.md)) is set to 0.75 and the vapor pressure deficit corresponding to the fraction given by _vpd_ is set to 4.00 kPa. If the user has actual data, they should use those values, otherwise the default values are adequate.
{% endhint %}

#### References

> Stockle et al. (1992)
