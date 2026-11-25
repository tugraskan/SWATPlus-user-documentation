---
description: "Chloride groundwater irrigation salt diagnostic"
---

# irsw_cl

**Printed heading:** `irsw_cl`, position 84 in the fixed 159-entry header. The mappings below apply to the eight-ion case in the order sulfate, calcium, magnesium, sodium, potassium, chloride, carbonate, bicarbonate. The writer uses `cs_db%num_salts` values per group; for another count, reconstruct the row from the WRITE list.

**Actual value:** `hsaltb_d(j)%salt(6)%irgw` ([daily writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L48); [record declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_module.f90#L7)). Chloride groundwater irrigation salt diagnostic.

**Unit:** kg/ha.

**Header mismatch:** The nominal heading denotes surface-water irrigation salt diagnostic, but the value at this position is `%irgw`. The omitted groundwater-upward-transfer group shifts the following values eight places to the left. Do not use the nominal label to assign the actual quantity or unit.

**Calculation**

The two groundwater producers are dormant in this revision. The legacy aquifer branch divides withdrawn ion mass by HRU area for soil delivery. The GWFlow allocation routine would add `irr_mass(8) / hru(hru_id)%area_ha` to the soil diagnostic when solute and salt transport are enabled. Its wetland branch uses the wetland irrigation diagnostic. Both routines lack active callers in the pinned source, leaving this field at its initialized or reset value in the traced execution path. [Legacy aquifer branch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_irrig.f90#L90) · [GWFlow solute branches](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/gwflow_pump_allo.f90#L118) · [Current GWFlow withdrawal branch](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_withdraw.f90#L126)

Monthly and yearly values sum the daily diagnostic. Average annual divides the accumulated yearly diagnostic by configured `time%nbyr`, giving the annual amount convention kg/ha/yr. The denominator is the configured simulation-year count, not a count of years contributing output; skipped or partial periods require care.

The corresponding period members are `hsaltb_m(j)%salt(6)%irgw`, `hsaltb_y(j)%salt(6)%irgw`, and `hsaltb_a(j)%salt(6)%irgw` ([monthly/yearly transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L95); [yearly/AA transfer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L191); [AA division](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_salt_output.f90#L288)).

See the [complete schema and period limitations](README.md#actual-data-layout). This page identifies the stored diagnostic and writer aggregation; it does not independently validate every upstream transport or application calculation.

[Back to the output table](README.md).
