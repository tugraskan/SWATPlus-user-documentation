---
description: Half-life of the pesticide in the soil
---

# hl\_soil

**Code reference:** `pestdb(ip)%soil_hlife` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pesticide_data_module.f90#L10)).

**Current use:** the daily surviving fraction is `exp(−0.693 / half-life)`; zero or less leaves nothing after one day ([`pest_parm_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_parm_read.f90#L63-L67)). With [exp\_sed](../../basin-1/parameters.bsn/exp_sed.md) = 1 in parameters.bsn it is treated as a 25 °C half-life and adjusted by layer temperature ([`pest_decay.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/pest_decay.f90#L49-L55)).

The half-life for a pesticide defines the number of days required for a given pesticide concentration to be reduced by one-half. The soil half-life entered for a pesticide is a lumped parameter that includes the net effect of volatilization, photolysis, hydrolysis, biological degradation, and chemical reactions.
