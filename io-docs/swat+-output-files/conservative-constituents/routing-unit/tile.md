---
description: "Mass in tile drainage (soil --> stream)"
---

# tile_seo4, tile_seo3, tile_born

**Code reference:** `rucsb_d(iru)%hd(5)%cs(ics)` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L53)).

**Printed header value:** `tile_seo4`, `tile_seo3`, `tile_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L529-L531)). The legend line reads `tile:         kg      mass in tile drainage             (soil --> stream)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L743)).

The routine comment calls `hd(5)` tile flow. This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`. [Routine comment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L26)

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../routing-unit.md).
