---
description: "Fraction of years to maturity completed"
---

# fr_yrmat

**Code reference:** `transpl(ic)%fr_yrmat` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/plant_data_module.f90#L159)).

Fraction of the plant's years to maturity already completed. The code multiplies it by mat_yrs to initialize integer plant age, with a minimum age of one, and also uses it in the perennial heat-unit state. Enter a fraction, not a duration in years.
