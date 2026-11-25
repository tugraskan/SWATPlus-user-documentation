---
description: "Mass transferred via sorption (soil --> sorbed mass)"
---

# sorb_seo4, sorb_seo3, sorb_born

**Code reference:** `hcsb_d(j)%cs(ics)%sorb` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L67)).

**Printed header value:** `sorb_seo4`, `sorb_seo3`, `sorb_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_module.f90#L260-L262)). The legend line reads `sorb:         kg/ha   mass transferred via sorption        (soil --> sorbed mass)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L216)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`, in the order seo4, seo3, boron.

**Type:** real (format `500e15.4`). **Unit:** kg/ha.

[Back to the output table](../hru.md).
