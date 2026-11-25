---
description: "Chloride dissolved-ion mass in the soil profile"
---

# soil_cl

**Printed heading:** `soil_cl`, position 12 in the fixed 159-entry header. The mappings below apply to the eight-ion case in the order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, bicarbonate. The writer uses `cs_db%num_salts` values per group; for another count, reconstruct the row from the WRITE list.

**Actual value:** `hsaltb_d(j)%salt(6)%soil` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L48); [record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L7)). Chloride dissolved-ion mass in the soil profile.

**Unit:** kg/ha.

The producer sums `cs_soil(j)%ly(jj)%salt(6)` over soil layers. It does not add the separate solid-mineral `salt_min` pool. Thus this is dissolved-ion profile mass, not dissolved plus solid-mineral salt ([profile sum](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L798); [dissolved mass conversion and separate solids](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L313)).

Monthly values sum the daily states and divide by the full calendar-month length, `ndays(time%mo + 1) - ndays(time%mo)`. Yearly values receive the unaveraged monthly sums and divide by `time%day_end_yr`. These divisors are not counts of actual output samples, which matters for partial periods.

Average annual receives the yearly sum **before** the yearly division, then divides only by configured `time%nbyr`. It is a daily-state sum per configured year, **not a mean state**; the missing day-count normalization is not corrected by labeling it an average.

The corresponding period members are `hsaltb_m(j)%salt(6)%soil`, `hsaltb_y(j)%salt(6)%soil`, and `hsaltb_a(j)%salt(6)%soil` ([monthly/yearly transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L95); [yearly/AA transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L191); [AA division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L288)).

See the [complete schema and period limitations](README.md#actual-data-layout).

[Back to the output table](README.md).
