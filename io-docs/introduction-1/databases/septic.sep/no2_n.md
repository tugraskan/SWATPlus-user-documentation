---
description: Nitrite nitrogen in the septic tank effluent
---

# no2\_n

**Code reference:** `sepdb(is)%no2concs` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L12)).

Intended to add, with `no3_n`, to biozone nitrate ([`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L171-L173)).

{% hint style="warning" %}
No effect in SWAT+ main (`6f515368`): the value enters the biozone calculations multiplied by the septic effluent inflow ([`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L121), [`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L170-L187)), and that inflow is set to zero and never given a value ([`zero1.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/zero1.f90#L48)). This comes from source reading, not a model run.
{% endhint %}

The concentration of NO2-N for a conventional system is typically very low.
