---
description: "Mass transferred via reaction (soil --> outside)"
---

# rctn_seo4, rctn_seo3, rctn_born

**Code reference:** `ru_hru_csb_d(iru)%cs(ics)%rctn` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L63)).

**Printed header value:** `rctn_seo4`, `rctn_seo3`, `rctn_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L569-L571)). The legend line reads `rctn:         kg      mass transferred via reaction     (soil --> outside)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L753)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`.

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../routing-unit.md).
