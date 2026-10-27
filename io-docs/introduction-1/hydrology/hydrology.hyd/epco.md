---
description: Plant uptake compensation factor
---

# epco

**Code reference:** `hyd_db(ithyd)%epco` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrology_data_module.f90#L12)).

The amount of water uptake that occurs on a given day is a function of the amount of water required by the plant for transpiration and the amount of water available in the soil. If upper layers in the soil profile do not contain enough water to meet the potential water uptake, users may allow lower layers to compensate.

{% hint style="info" %}
As _epco_ approaches 1.0, the model allows more of the water uptake demand to be met by lower layers in the soil. As _epco_ approaches 0.0, the model allows less variation from the original depth distribution to take place.
{% endhint %}
