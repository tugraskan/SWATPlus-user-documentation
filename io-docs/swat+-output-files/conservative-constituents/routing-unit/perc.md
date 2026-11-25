---
description: "Mass in deep percolation (soil --> aquifer)"
---

# perc_seo4, perc_seo3, perc_born

**Code reference:** `rucsb_d(iru)%hd(2)%cs(ics)` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L50)).

**Printed header value:** `perc_seo4`, `perc_seo3`, `perc_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L517-L519)). The legend line reads `perc:         kg      mass in deep percolation          (soil --> aquifer)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L740)).

The routine comment calls `hd(2)` percolation. This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`. [Routine comment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L23)

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../routing-unit.md).
