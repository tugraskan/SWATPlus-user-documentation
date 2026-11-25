---
description: "Potassium road-salt application diagnostic"
---

# dryd_k

**Printed heading:** `dryd_k`, position 115 in the fixed 159-entry header. The mappings below apply to the eight-ion case in the order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, bicarbonate. The writer uses `cs_db%num_salts` values per group; for another count, reconstruct the row from the WRITE list.

**Actual value:** `hsaltb_d(j)%salt(5)%road` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L48); [record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L7)). Potassium road-salt application diagnostic.

**Unit:** kg/ha.

**Header mismatch:** The nominal heading denotes dry-deposition salt diagnostic, but the value at this position is `%road`. The omitted groundwater-upward-transfer group shifts the following values eight places to the left. Do not use the nominal label to assign the actual quantity or unit.

**Calculation**

The producer adds road salt directly to the top soil layer. It divides monthly loading by the calendar month length and average-annual loading by 365. In yearly mode the reader distributes the annual mass across days with positive precipitation and mean air temperature below 0 °C, in proportion to each qualifying day’s precipitation. A year with no qualifying days has zero daily allocations. The reader allocates the road-salt array only when `salt_road` exists. The application routine accesses the array in the applicable timestep branch without an allocation check. [Yearly daily allocation](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_roadsalt_read.f90#L73) · [Daily soil application](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_roadsalt.f90#L34) · [Allocation guard](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_roadsalt_read.f90#L36)

Monthly and yearly values sum the daily diagnostic. Average annual divides the accumulated yearly diagnostic by configured `time%nbyr`, giving the annual amount convention kg/ha/yr. The denominator is the configured simulation-year count, not a count of years contributing output; skipped or partial periods require care.

The corresponding period members are `hsaltb_m(j)%salt(5)%road`, `hsaltb_y(j)%salt(5)%road`, and `hsaltb_a(j)%salt(5)%road` ([monthly/yearly transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L95); [yearly/AA transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L191); [AA division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L288)).

See the [complete schema and period limitations](README.md#actual-data-layout). This page identifies the stored diagnostic and writer aggregation; it does not independently validate every upstream transport or application calculation.

[Back to the output table](README.md).
