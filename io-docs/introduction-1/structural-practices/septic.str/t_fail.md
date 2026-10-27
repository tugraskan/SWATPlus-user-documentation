---
description: Time until failing systems gets fixed
---

# t\_fail

**Code reference:** `sep(isep)%tfail`

**Declared type:** `septic_system` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sep_read.f90#L43), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/septic_data_module.f90#L27)).

An active system becomes failing as the biozone gets clogged and hydraulic failure occurs. A failing system automatically turns active during the simulation and septic parameters are re-initialized to default values after the specified number of days for rehabilitation. For testing long term failure, _t\_fail_ can be increased as per the failing duration. The parameter [operation](operation.md) should be set to 2 for simulating failing conditions.
