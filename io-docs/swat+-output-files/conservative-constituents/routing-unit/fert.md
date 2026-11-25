---
description: "Mass in applied fertilizer (outside --> soil)"
---

# fert_seo4, fert_seo3, fert_born

**Code reference:** `ru_hru_csb_d(iru)%cs(ics)%fert` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L61)).

**Printed header value:** `fert_seo4`, `fert_seo3`, `fert_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L561-L563)). The legend line reads `fert:         kg      mass in applied fertilizer        (outside --> soil)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L751)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`.

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../routing-unit.md).
