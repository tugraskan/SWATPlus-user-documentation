---
description: Half-life of the pesticide on the foliage
---

# hl\_foliage

**Code reference:** `pestdb(ip)%foliar_hlife` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L9)).

**Current use:** the daily surviving fraction is `exp(−0.693 / half-life)`; zero or less leaves nothing after one day ([`pest_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_parm_read.f90#L58-L62)). With [exp\_sed](../../basin-1/parameters.bsn/exp_sed.md) = 1 in parameters.bsn the value is treated as a 25 °C half-life and adjusted using the top soil layer temperature ([`pest_decay.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_decay.f90#L76-L83)).

The half-life for a pesticide defines the number of days required for a given pesticide concentration to be reduced by one-half. The half-life entered for a pesticide is a lumped parameter that includes the net effect of volatilization, photolysis, hydrolysis, biological degradation and chemical reactions.

For most pesticides, the foliar half-life is much less than the soil half-life due to enhanced volatilization and photodecomposition. If the foliar half-life is available for the pesticide this value should be used. If the foliar half-life is not available, the foliar half-life can be estimated using the following rules:

1. Foliar half-life is assumed to be less than the soil half-life by a factor of 0.5 to 0.25, depending on vapor pressure and sensitivity to photodegradation.
2. Foliar half-life is adjusted downward for pesticides with vapor pressures less than 10-5 mm Hg.
3. The maximum foliar half-life assigned is 30 days.
