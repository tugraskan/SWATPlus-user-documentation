---
description: Beginning month of the mid-year nutrient settling period
---

# mid\_start

**Code reference:** `res_nut(ires)%ires1` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L111)).

The model allows the user to define two settling rates for each nutrient and the time of the year during which each settling rate is used. A variation in settling rates is allowed so that impact of temperature and other seasonal factors may be accounted for in the modeling of nutrient settling. To use only one settling rate for the entire year, both variables for the nutrient may be set to the same value. Setting all variables to zero will cause the model to ignore settling of nutrients in the water body.
