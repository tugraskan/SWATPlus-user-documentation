---
description: Available water capacity of the soil layer
---

# awc

**Code reference:** `soildb(isol)%ly(j)%awc` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/soil_data_module.f90#L49)).

The plant available water content, also referred to as the available water capacity, is calculated by subtracting the fraction of the water content at permanent wilting point from the water content at field capacity, _AWC = FC - WP_. Available water capacity is estimated by determining the amount of water released between in situ field capacity (the soil water content at soil matric potential of -0.033 MPa) and the permanent wilting point (the soil water content at soil matric potential of -1.5 MPa).
