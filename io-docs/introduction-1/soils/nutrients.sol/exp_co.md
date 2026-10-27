---
description: Depth coefficient to adjust nutrient concentrations for depth
---

# exp\_co

Depth coefficient, in 1/mm, used to calculate the layer depth factor as exp(-exp_co * depth), where depth is the depth to the bottom of the soil layer in mm. If exp_co is greater than 0.005, SWAT+ main (6f515368) replaces it with 0.001.
