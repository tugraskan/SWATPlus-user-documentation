---
description: 7-day Biological Oxygen Demand (BOD) of the septic tank effluent
---

# bod

**Code reference:** `sepdb(is)%bodconcs` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/septic_data_module.f90#L8)).

Intended to add to the biozone BOD load and drive biomass growth ([`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L187)).

{% hint style="warning" %}
No effect in SWAT+ main (`6f515368`): the value enters the biozone calculations multiplied by the septic effluent inflow ([`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L121), [`sep_biozone.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sep_biozone.f90#L170-L187)), and that inflow is set to zero and never given a value ([`zero1.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/zero1.f90#L48)). This comes from source reading, not a model run.
{% endhint %}

The BOD for a conventional system is typically 170 mg/L. The value varies greatly for different types of septic systems (see Table A-1 of Siegrist et al. (2005)).

#### References

> Siegrist et al. (2005)
