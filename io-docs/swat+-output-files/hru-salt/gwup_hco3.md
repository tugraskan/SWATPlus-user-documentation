---
description: "Bicarbonate wetland-seepage salt diagnostic"
---

# gwup_hco3

**Printed heading:** `gwup_hco3`, position 70 in the fixed 159-entry header. The mappings below apply to the eight-ion case in the order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, bicarbonate. The writer uses `cs_db%num_salts` values per group; for another count, reconstruct the row from the WRITE list.

**Actual value:** `hsaltb_d(j)%salt(8)%wtsp` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L48); [record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L7)). Bicarbonate wetland-seepage salt diagnostic.

**Unit:** kg/ha.

**Header mismatch:** The nominal heading denotes groundwater-to-soil salt diagnostic, but the value at this position is `%wtsp`. The omitted groundwater-upward-transfer group shifts the following values eight places to the left. Do not use the nominal label to assign the actual quantity or unit.

**Producer and interpretation:** [Wetland seepage calculation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_salt.f90#L62) computes a seepage loss in kg from seepage volume times salt concentration, capped by the wetland's mass remaining after outflow. It divides by **HRU area** in ha, adds the result to the top soil layer, and stores it in `wtspsalt(j,8)` ([soil addition](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wet_salt.f90#L92)). This is the input to soil at the wetland step; it does not measure how much of that input remains after soil transport. It does not use the runoff lag buffer.

Monthly and yearly values sum the daily diagnostic. Average annual divides the accumulated yearly diagnostic by configured `time%nbyr`, giving the annual amount convention kg/ha/yr. The denominator is the configured simulation-year count, not a count of years contributing output; skipped or partial periods require care.

The corresponding period members are `hsaltb_m(j)%salt(8)%wtsp`, `hsaltb_y(j)%salt(8)%wtsp`, and `hsaltb_a(j)%salt(8)%wtsp` ([monthly/yearly transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L95); [yearly/AA transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L191); [AA division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L288)).

The `%gwup` diagnostic is assigned in [the HRU controller](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_control.f90#L796), but this output writer omits it. Groundwater-to-soil salt transfer cannot be recovered from this heading's value. The intended `gwupsalt` producer would add `hru_soil(j,jj,10)` across layers, but [its guard](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_lch.f90#L51) uses a local `gw_soil_flag` initialized to zero with no enabling assignment. That branch stays off in this source; enabling the global GWFlow soil-exchange setting does not change the local flag.

See the [complete schema and period limitations](README.md#actual-data-layout). This page identifies the stored diagnostic and writer aggregation; it does not independently validate every upstream transport or application calculation.

[Back to the output table](README.md).
