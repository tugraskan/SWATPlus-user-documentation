---
description: Annual loss-rate coefficient for soluble phosphorus
---

# secchi_co

**Code reference:** `res_nut(ires)%psolr`

**Declared type:** `reservoir_nut_data` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/res_read_nut.f90#L55), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/reservoir_data_module.f90#L118)).

Despite the legacy input label, this field is the annual loss-rate coefficient for soluble phosphorus, not a water-clarity coefficient. SWAT+ divides the input by 365 and applies the daily coefficient in reservoir and wetland nutrient loss.
