---
description: "net dissolved-ion mass change across soil chemistry"
---

# conc_so4

**Printed heading:** `conc_so4`, position 151 in the fixed 159-entry header. The mappings below apply to the eight-ion case in the order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, bicarbonate. The writer uses `cs_db%num_salts` values per group; for another count, reconstruct the row from the WRITE list.

**Actual value:** `hsaltb_d(j)%salt(1)%diss` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L48); [record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L7)). Net dissolved-ion mass change across soil chemistry, summed across ions and soil layers; storage in salt(1) does not make it sulfate-only.

**Unit:** kg/ha.

**Header mismatch:** The nominal heading denotes unweighted mean of soil-layer ion concentrations, but the value at this position is `%diss`. The omitted groundwater-upward-transfer group shifts the following values eight places to the left. Do not use the nominal label to assign the actual quantity or unit.

The producer sets `diss = mass_after - mass_before` after converting the dissolved-ion sums to kg/ha. Positive means net gain to dissolved ions and negative means net loss across the chemistry routine; this is not a gross positive-only mineral-dissolution total ([before mass](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L133); [after mass](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L313); [signed diagnostic](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_chem_hru.f90#L366)).

Monthly and yearly values sum the daily diagnostic. Average annual accumulates yearly values but **does not divide this scalar by `time%nbyr`**; it remains a cumulative kg/ha diagnostic for the years that reach the accumulator, not an average annual amount.

The corresponding period members are `hsaltb_m(j)%salt(1)%diss`, `hsaltb_y(j)%salt(1)%diss`, and `hsaltb_a(j)%salt(1)%diss` ([monthly/yearly transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L95); [yearly/AA transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L191); [AA division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L288)).

If reconstructing the intended concentration field, `hsaltb_d(j)%salt(1)%conc` is actually at position 143, under the printed heading [`uptk_so4`](uptk_so4.md). Its daily/monthly/yearly component unit is g/m3 (= mg/L). Its average-annual calculation lacks day-count normalization, so it is not a mean concentration.

See the [complete schema and period limitations](README.md#actual-data-layout).

[Back to the output table](README.md).
