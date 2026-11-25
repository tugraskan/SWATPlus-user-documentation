---
description: "Mass in dry deposition (outside --> soil)"
---

# dryd_seo4, dryd_seo3, dryd_born

**Code reference:** `ru_hru_csb_d(iru)%cs(ics)%dryd` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L60)).

**Printed header value:** `dryd_seo4`, `dryd_seo3`, `dryd_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L557-L559)). The legend line reads `dryd:         kg      mass in dry deposition            (outside --> soil)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L750)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`.

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../routing-unit.md).
