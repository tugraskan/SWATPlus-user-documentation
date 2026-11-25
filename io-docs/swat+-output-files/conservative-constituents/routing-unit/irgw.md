---
description: "Mass in groundwater irrigation (aquifer --> soil)"
---

# irgw_seo4, irgw_seo3, irgw_born

**Code reference:** `ru_hru_csb_d(iru)%cs(ics)%irgw` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L57)).

**Printed header value:** `irgw_seo4`, `irgw_seo3`, `irgw_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L545-L547)). The legend line reads `irgw:         kg      mass in groundwater irrigation    (aquifer --> soil)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L747)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`.

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../routing-unit.md).
