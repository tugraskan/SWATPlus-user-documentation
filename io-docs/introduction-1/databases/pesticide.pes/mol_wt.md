---
description: Molecular weight to calculate mixing velocity
---

# mol\_wt

**Code reference:** `pestdb(ip)%mol_wt` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L14)).

**Current use:** sets the water–sediment mixing velocity in channels, proportional to `mol_wt^(−0.6666)` ([`sd_hydsed_init.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/sd_hydsed_init.f90#L268)), and converts parent mass to metabolite mass ([`pest_decay.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_decay.f90#L62-L63)). Do not leave it at 0 for a pesticide that is simulated.

{% hint style="warning" %}
Suspected defect (source reading): reservoirs set the mixing velocity to `mol_wt × porosity` ([`res_initial.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_initial.f90#L113)), which increases with molecular weight, unlike the channel formula.
{% endhint %}
