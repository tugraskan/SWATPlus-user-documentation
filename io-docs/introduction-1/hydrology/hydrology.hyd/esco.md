---
description: Soil evaporation compensation factor
---

# esco

**Code reference:** `hyd_db(ithyd)%esco` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/hydrology_data_module.f90#L11)).

This coefficient has been incorporated to allow the user to modify the depth distribution used to meet the soil evaporative demand to account for the effect of capillary action, crusting and cracks.

{% hint style="info" %}
As the value for _esco_ is increased, the model is able to extract more of the evaporative demand from lower levels.&#x20;
{% endhint %}
