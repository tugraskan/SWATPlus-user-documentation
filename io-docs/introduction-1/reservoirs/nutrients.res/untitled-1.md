---
description: Annual loss-rate coefficient for soluble inorganic nitrogen
---

# chla_co

**Code reference:** `res_nut(ires)%nsolr` ([declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L117)).

Despite the legacy input label, this field is the annual loss-rate coefficient for soluble inorganic nitrogen (NO3, NH3, and NO2), not a chlorophyll-a production coefficient. SWAT+ divides the input by 365 and applies the daily coefficient in reservoir and wetland nutrient loss.
