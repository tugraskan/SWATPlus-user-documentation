---
description: "Mass in wetland seepage (wetland --> soil)"
---

# wtsp_seo4, wtsp_seo3, wtsp_born

**Code reference:** `ru_hru_csb_d(iru)%cs(ics)%wtsp` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L55)).

**Printed header value:** `wtsp_seo4`, `wtsp_seo3`, `wtsp_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L537-L539)). The legend line reads `wtsp:         kg      mass in wetland seepage           (wetland --> soil)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L745)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`.

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../routing-unit.md).
