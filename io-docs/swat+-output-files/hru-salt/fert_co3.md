---
description: "Carbonate soil-amendment salt diagnostic"
---

# fert_co3

**Printed heading:** `fert_co3`, position 133 in the fixed 159-entry header. The mappings below apply to the eight-ion case in the order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, bicarbonate. The writer uses `cs_db%num_salts` values per group; for another count, reconstruct the row from the WRITE list.

**Actual value:** `hsaltb_d(j)%salt(7)%amnd` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L48); [record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L7)). Carbonate soil-amendment salt diagnostic.

**Unit:** kg/ha.

**Header mismatch:** The nominal heading denotes fertilizer salt diagnostic, but the value at this position is `%amnd`. The omitted groundwater-upward-transfer group shifts the following values eight places to the left. Do not use the nominal label to assign the actual quantity or unit.

**Calculation**

The scheduled and decision-table manure operations can call `salt_fert`. With salts enabled, the routine uses the `manure_db(ifrt)%iorg_min > 1` gate and a positive fertilizer index. It adds `xx * frt_kg * fert_salt(ifrt)%co3` to each of the top two layers using complementary application fractions. A fertilizer name beginning with lowercase `a` puts the addition in `amnd`. The reader describes the stored ion values as kg/ha and reads them directly. The multiplication needs a dimensionless ion fraction to yield the reported kg/ha, so the source leaves the unit contract unresolved. The application routine also uses the table without checking whether the reader allocated it. [Soil application and classification](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_fert.f90#L29) · [Table units and allocation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_fert_read.f90#L21)

Monthly and yearly values sum the daily diagnostic. Average annual divides the accumulated yearly diagnostic by configured `time%nbyr`, giving the annual amount convention kg/ha/yr. The denominator is the configured simulation-year count, not a count of years contributing output; skipped or partial periods require care.

The corresponding period members are `hsaltb_m(j)%salt(7)%amnd`, `hsaltb_y(j)%salt(7)%amnd`, and `hsaltb_a(j)%salt(7)%amnd` ([monthly/yearly transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L95); [yearly/AA transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L191); [AA division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L288)).

See the [complete schema and period limitations](README.md#actual-data-layout). This page identifies the stored diagnostic and writer aggregation; it does not independently validate every upstream transport or application calculation.

[Back to the output table](README.md).
