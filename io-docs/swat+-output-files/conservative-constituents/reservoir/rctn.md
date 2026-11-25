---
description: "Mass consumed due to chemical reaction"
---

# seo4_rctn, seo3_rctn, born_rctn

**Code reference:** `rescs_d(j)%cs(ics)%rctn` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L49)).

**Printed header value:** `seo4_rctn`, `seo3_rctn`, `born_rctn` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L76-L78)). The legend line reads `rctn:        kg       mass consumed due to chemical reaction` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L611)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`, in the order seo4, seo3, boron.

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../reservoir.md).
