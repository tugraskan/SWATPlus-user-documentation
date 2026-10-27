---
description: ​Average area of drainfield of individual septic systems
---

# area

**Code reference:** `sep(isep)%area`

**Declared type:** `septic_system` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sep_read.f90#L43), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/septic_data_module.f90#L26)).

The typically recommended drainfield area per person is about 40 to 70 square meters. This varies from state to state in the United States. For a household with 2.5 people, a drainfield area of 100 square meters is generally recommended. Users can modify the area based on the number of people in a household. SWAT+ main (6f515368) reads `area` and `residents` but does not use either value in model calculations, so changing them does not affect model results.
