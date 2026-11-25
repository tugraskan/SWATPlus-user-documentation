---
description: "Mass in sediment runoff (soil --> stream)"
---

# sedm_seo4, sedm_seo3, sedm_born

**Code reference:** `hcsb_d(j)%cs(ics)%sedm` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L52)).

**Printed header value:** `sedm_seo4`, `sedm_seo3`, `sedm_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_module.f90#L196-L198)). The legend line reads `sedm:         kg/ha   mass in sediment runoff              (soil --> stream)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L200)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`, in the order seo4, seo3, boron.

**Type:** real (format `500e15.4`). **Unit:** kg/ha.

[Back to the output table](../hru.md).
