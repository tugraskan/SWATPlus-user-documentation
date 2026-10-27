---
description: Removal efficiency of sweeping operation
---

# swp\_eff

The removal efficiency of street sweeping is a function of the type of sweeper, whether flushing is a part of the street cleaning process, the quantity of total solids, the frequency of rainfall events and the constituents considered. Removal efficiency can vary depending on the constituent being considered, with efficiencies being greater for particulate constituents. The removal efficiencies for nitrogen and phosphorus are typically less than the solid removal efficiency (Pitt, 1979).

Because SWAT+ assumes a set concentration of nutrient constituents in the solids, the same removal efficiency is in effect used for all constituents.&#x20;

{% hint style="info" %}
A value of 0.0 removes none of the built-up sediment. A value of 1.0 removes all sediment associated with the sweepable curb length. The overall removed fraction is `frac_curb * swp_eff`, so complete removal requires both values to be 1.0.
{% endhint %}

#### References

> Pitt (1979)
