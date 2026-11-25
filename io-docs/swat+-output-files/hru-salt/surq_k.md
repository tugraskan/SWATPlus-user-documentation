---
description: "Potassium surface-runoff salt diagnostic"
---

# surq_k

**Printed heading:** `surq_k`, position 19 in the fixed 159-entry header. The mappings below apply to the eight-ion case in the order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, bicarbonate. The writer uses `cs_db%num_salts` values per group; for another count, reconstruct the row from the WRITE list.

**Actual value:** `hsaltb_d(j)%salt(5)%surq` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L48); [record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L7)). Potassium surface-runoff salt diagnostic.

**Unit:** kg/ha.

**Producer and interpretation:** [Soil leaching](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_lch.f90#L124) calculates a surface-runoff loss from the top layer as runoff depth times `cosurfsalt`, capped by the available dissolved ion mass. It subtracts that loss from the layer. [Surface lag storage](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/stor_surfstor.f90#L144) adds the new loss to `surf_bs(24,j)`, assigns `surqsalt(j,5)` to `surf_bs(24,j) * brt(j)`, and retains the unreleased remainder. This is the released mass per HRU area, which can include earlier days' runoff. It is not the raw same-day soil loss.

Monthly and yearly values sum the daily diagnostic. Average annual divides the accumulated yearly diagnostic by configured `time%nbyr`, giving the annual amount convention kg/ha/yr. The denominator is the configured simulation-year count, not a count of years contributing output; skipped or partial periods require care.

The corresponding period members are `hsaltb_m(j)%salt(5)%surq`, `hsaltb_y(j)%salt(5)%surq`, and `hsaltb_a(j)%salt(5)%surq` ([monthly/yearly transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L95); [yearly/AA transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L191); [AA division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L288)).

See the [complete schema and period limitations](README.md#actual-data-layout). This page identifies the stored diagnostic and writer aggregation; it does not independently validate every upstream transport or application calculation.

[Back to the output table](README.md).
