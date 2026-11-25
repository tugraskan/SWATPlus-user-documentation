---
description: "Mass in surface water irrigation (channel --> soil)"
---

# irsw_seo4, irsw_seo3, irsw_born

**Code reference:** `hcsb_d(j)%cs(ics)%irsw` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L59)).

**Printed header value:** `irsw_seo4`, `irsw_seo3`, `irsw_born` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_module.f90#L228-L230)). The legend line reads `irsw:         kg/ha   mass in surfac water irrigation      (channel --> soil)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L208)). The legend spells "surfac" in the source.

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`, in the order seo4, seo3, boron.

**Type:** real (format `500e15.4`). **Unit:** kg/ha.

[Back to the output table](../hru.md).
