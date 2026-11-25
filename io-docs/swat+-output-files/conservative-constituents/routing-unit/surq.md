---
description: "Mass in surface runoff (soil --> stream)"
---

# surq_seo4, surq_seo3, surq_born

**Code reference:** `rucsb_d(iru)%hd(3)%cs(ics)` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L51)).

**Printed header value:** `surq_seo4`, `surq_seo3`, `surq_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L521-L523)). The legend line reads `surq:         kg      mass in surface runoff            (soil --> stream)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L741)).

The routine comment calls `hd(3)` surface runoff. This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`. [Routine comment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L24)

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../routing-unit.md).
