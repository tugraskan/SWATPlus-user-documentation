---
description: "Name identifying this component-value record"
---

# om_treat_name

**Code reference:** `om_treat_name(iom_tr)` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_allocation_module.f90#L217), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_treat_read.f90#L43)).

16-character name identifying a treatment organic/mineral record. Matched against `org_min_name` in [water_treat.wal](../water_treat.wal/README.md) when `org_min_typ == "const"` ([`water_treatment_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_treatment_read.f90#L65)), and printed in treatment output files ([`wallo_treat_output.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/wallo_treat_output.f90#L19,L22,L35,L38,L52,L55,L70,L73)).
