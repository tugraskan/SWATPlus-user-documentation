---
description: "Calcium unweighted mean of soil-layer ion concentrations"
---

# uptk_ca

**Printed heading:** `uptk_ca`, position 144 in the fixed 159-entry header. The mappings below apply to the eight-ion case in the order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, bicarbonate. The writer uses `cs_db%num_salts` values per group; for another count, reconstruct the row from the WRITE list.

**Actual value:** `hsaltb_d(j)%salt(2)%conc` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L48); [record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L7)). Calcium unweighted mean of soil-layer ion concentrations.

**Unit:** g/m3. This is numerically equivalent to mg/L, as used in the source declaration.

**Header mismatch:** The nominal heading denotes plant-uptake salt diagnostic, but the value at this position is `%conc`. The omitted groundwater-upward-transfer group shifts the following values eight places to the left. Do not use the nominal label to assign the actual quantity or unit.

The producer sums `cs_soil(j)%ly(jj)%saltc(2)` and divides by `soil(j)%nly`; it does not weight layers by water volume or thickness ([layer mean](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L798)).

Monthly values sum the daily states and divide by the full calendar-month length, `ndays(time%mo + 1) - ndays(time%mo)`. Yearly values receive the unaveraged monthly sums and divide by `time%day_end_yr`. These divisors are not counts of actual output samples, which matters for partial periods.

Average annual receives the yearly sum **before** the yearly division, then divides only by configured `time%nbyr`. It is a daily-state sum per configured year, **not a mean state**; the missing day-count normalization is not corrected by labeling it an average.

The corresponding period members are `hsaltb_m(j)%salt(2)%conc`, `hsaltb_y(j)%salt(2)%conc`, and `hsaltb_a(j)%salt(2)%conc` ([monthly/yearly transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L95); [yearly/AA transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L191); [AA division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L288)).

See the [complete schema and period limitations](README.md#actual-data-layout).

[Back to the output table](README.md).
