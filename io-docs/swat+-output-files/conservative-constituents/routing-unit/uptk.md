---
description: "Mass in plant uptake (soil --> outside)"
---

# uptk_seo4, uptk_seo3, uptk_born

**Code reference:** `ru_hru_csb_d(iru)%cs(ics)%uptk` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L62)).

**Printed header value:** `uptk_seo4`, `uptk_seo3`, `uptk_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L565-L567)). The legend line reads `uptk:         kg      mass in plant uptake              (soil --> outside)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L752)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`.

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../routing-unit.md).
