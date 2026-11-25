---
description: "Mass in plant uptake (soil --> outside)"
---

# uptk_seo4, uptk_seo3, uptk_born

**Code reference:** `hcsb_d(j)%cs(ics)%uptk` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L65)).

**Printed header value:** `uptk_seo4`, `uptk_seo3`, `uptk_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_module.f90#L252-L254)). The legend line reads `uptk:         kg/ha   mass in plant uptake                 (soil --> outside)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L214)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`, in the order seo4, seo3, boron.

**Type:** real (format `500e15.4`). **Unit:** kg/ha.

[Back to the output table](../hru.md).
