---
description: "Mass transferred via sorption (soil --> sorbed mass)"
---

# sorb_seo4, sorb_seo3, sorb_born

**Code reference:** `ru_hru_csb_d(iru)%cs(ics)%sorb` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L64)).

**Printed header value:** `sorb_seo4`, `sorb_seo3`, `sorb_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L573-L575)). The legend line reads `sorb:         kg      mass transferred via sorption     (soil --> sorbed mass)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L754)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`. It is the last group of the row.

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../routing-unit.md).
