---
description: "Simulation year (integer) identifying the start of the year for which the CO2 value is defined"
---

# iyr

**Code reference:** `co2_inc%co2_yr(itot)%iyr` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/co2_read.f90#L24)).

Simulation year (integer) identifying the start of the year for which the CO2 value is defined.

The reader uses the first and last year to locate the series. Inside that span it advances by row position, so keep the years consecutive and in ascending order. See [co2_read.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/co2_read.f90#L77-L103).
