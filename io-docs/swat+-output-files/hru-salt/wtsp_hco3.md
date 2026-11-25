---
description: "Bicarbonate surface-water irrigation salt diagnostic"
---

# wtsp_hco3

**Printed heading:** `wtsp_hco3`, position 78 in the fixed 159-entry header. The mappings below apply to the eight-ion case in the order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, bicarbonate. The writer uses `cs_db%num_salts` values per group; for another count, reconstruct the row from the WRITE list.

**Actual value:** `hsaltb_d(j)%salt(8)%irsw` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L48); [record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L7)). Bicarbonate surface-water irrigation salt diagnostic.

**Unit:** kg/ha.

**Header mismatch:** The nominal heading denotes wetland-seepage salt diagnostic, but the value at this position is `%irsw`. The omitted groundwater-upward-transfer group shifts the following values eight places to the left. Do not use the nominal label to assign the actual quantity or unit.

**Calculation**

The surface-water assignment is in the dormant `salt_irrig` routine. Its reservoir, channel, and diversion branches calculate ion mass from water volume and concentration, then divide by HRU area for a soil delivery. A delivery to a wetland goes to the wetland irrigation diagnostic. The water allocation call is commented out in this revision, leaving this field at its initialized or reset value in the traced execution path. [Legacy irrigation branches](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_irrig.f90#L63) · [Commented call](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/wallo_pou_deliv.f90#L60)

Monthly and yearly values sum the daily diagnostic. Average annual divides the accumulated yearly diagnostic by configured `time%nbyr`, giving the annual amount convention kg/ha/yr. The denominator is the configured simulation-year count, not a count of years contributing output; skipped or partial periods require care.

The corresponding period members are `hsaltb_m(j)%salt(8)%irsw`, `hsaltb_y(j)%salt(8)%irsw`, and `hsaltb_a(j)%salt(8)%irsw` ([monthly/yearly transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L95); [yearly/AA transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L191); [AA division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L288)).

See the [complete schema and period limitations](README.md#actual-data-layout). This page identifies the stored diagnostic and writer aggregation; it does not independently validate every upstream transport or application calculation.

[Back to the output table](README.md).
