---
description: "Mass in soil lateral flow (soil --> stream)"
---

# latq_seo4, latq_seo3, latq_born

**Code reference:** `rucsb_d(iru)%hd(4)%cs(ics)` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L52)).

**Printed header value:** `latq_seo4`, `latq_seo3`, `latq_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/constituent_mass_module.f90#L525-L527)). The legend line reads `latq:         kg      mass in soil lateral flow         (soil --> stream)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L742)).

The routine comment calls `hd(4)` soil lateral flow. This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`. [Routine comment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ru_cs_output.f90#L25)

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../routing-unit.md).
