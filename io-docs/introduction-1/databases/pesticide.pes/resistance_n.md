---
description: Soil water used for the plant uptake concentration
---

# resistance\_n

**Code reference:** `pestdb(ip)%resistance_n`

**Declared type:** `pesticide_db` ([reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pest_parm_read.f90#L48), [declaration](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/pesticide_data_module.f90#L22)).

Sets which soil water content is used to compute the pesticide concentration for plant uptake:

* 0: use the actual soil water content
* 1 (default): use the field-capacity water content
* between 0 and 1: a linear blend, soil water = actual + resistance\_n × max(0, field capacity − actual)
