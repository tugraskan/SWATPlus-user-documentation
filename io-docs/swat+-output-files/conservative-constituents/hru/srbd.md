---
description: "Mass sorbed in soil profile"
---

# seo4_srbd, seo3_srbd, born_srbd

**Code reference:** `hcsb_d(j)%cs(ics)%srbd` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/hru_cs_output.f90#L69)).

**Printed header value:** `seo4_srbd`, `seo3_srbd`, `born_srbd` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_module.f90#L268-L270)). The legend line reads `srbd:         kg/ha   mass sorbed in soil profile` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L218)). The source comment above the header names says the value is the total over the layers. [Comment](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cs_module.f90#L267)

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`, in the order seo4, seo3, boron. It is the last group of the row. Unlike the other headers, the constituent name follows the group name in this one.

**Type:** real (format `500e15.4`). **Unit:** kg/ha.

[Back to the output table](../hru.md).
