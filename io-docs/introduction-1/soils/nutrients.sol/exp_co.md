---
description: Depth coefficient to adjust nutrient concentrations for depth
---

# exp\_co

**Code reference:** `solt_db(isolt)%exp_co` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/soil_data_module.f90#L15)).

Depth coefficient, in 1/mm, used to calculate the layer depth factor as exp(-exp_co * depth), where depth is the depth to the bottom of the soil layer in mm. If exp_co is greater than 0.005, SWAT+ main (6f515368) replaces it with 0.001.
