---
description: "Mass in urban runoff (soil --> stream)"
---

# urbq_seo4, urbq_seo3, urbq_born

**Code reference:** `hcsb_d(j)%cs(ics)%urbq` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L54)).

**Printed header value:** `urbq_seo4`, `urbq_seo3`, `urbq_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_module.f90#L204-L206)). The legend line reads `urbq:         kg/ha   mass in urban runoff                 (soil --> stream)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L202)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`, in the order seo4, seo3, boron.

**Type:** real (format `500e15.4`). **Unit:** kg/ha.

[Back to the output table](../hru.md).
