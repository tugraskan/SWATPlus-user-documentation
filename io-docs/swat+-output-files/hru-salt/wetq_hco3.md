---
description: "Bicarbonate wetland-runoff salt diagnostic"
---

# wetq_hco3

**Printed heading:** `wetq_hco3`, position 46 in the fixed 159-entry header. The mappings below apply to the eight-ion case in the order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, bicarbonate. The writer uses `cs_db%num_salts` values per group; for another count, reconstruct the row from the WRITE list.

**Actual value:** `hsaltb_d(j)%salt(8)%wetq` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L48); [record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L7)). Bicarbonate wetland-runoff salt diagnostic.

**Unit:** kg/ha.

**Producer and interpretation:** [Wetland salt balance](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_salt.f90#L42) computes outflow mass from outflow volume and the salt concentration at entry to the salt routine, capped by available wetland salt. It divides that mass in kg by HRU area in ha to make the initial `wetqsalt(j,8)`. [Wetland lag release](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/stor_surfstor.f90#L231) replaces it with `surf_bs(43,j) * brt(j)` after adding the new mass to the buffer. The HRU output is the released, lagged outflow per HRU area; the separate wetland outflow diagnostic is stored before that lag.

Monthly and yearly values sum the daily diagnostic. Average annual divides the accumulated yearly diagnostic by configured `time%nbyr`, giving the annual amount convention kg/ha/yr. The denominator is the configured simulation-year count, not a count of years contributing output; skipped or partial periods require care.

The corresponding period members are `hsaltb_m(j)%salt(8)%wetq`, `hsaltb_y(j)%salt(8)%wetq`, and `hsaltb_a(j)%salt(8)%wetq` ([monthly/yearly transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L95); [yearly/AA transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L191); [AA division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L288)).

See the [complete schema and period limitations](README.md#actual-data-layout). This page identifies the stored diagnostic and writer aggregation; it does not independently validate every upstream transport or application calculation.

[Back to the output table](README.md).
