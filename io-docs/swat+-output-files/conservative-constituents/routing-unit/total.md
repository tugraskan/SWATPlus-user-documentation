---
description: "Total constituent mass out"
---

# total_seo4, total_seo3, total_born

**Code reference:** `rucsb_d(iru)%hd(1)%cs(ics)` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L49)).

**Printed header value:** `total_seo4`, `total_seo3`, `total_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L513-L515)). The legend line reads `total:        kg      mass = perc + surq + latq + tile` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L739)).

The source comment in the routine calls `hd(1)` the total constituent out. The comment above the header names says total is surq + latq + tile, while the legend line also includes perc; the two descriptions differ. [Routine comment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L22), [Header comment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L512) This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`.

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../routing-unit.md).
