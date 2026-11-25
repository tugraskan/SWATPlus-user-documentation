---
description: "Mass settling to bottom of reservoir"
---

# seo4_setl, seo3_setl, born_setl

**Code reference:** `rescs_d(j)%cs(ics)%settle` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L48)).

**Printed header value:** `seo4_setl`, `seo3_setl`, `born_setl` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L73-L75)). The legend line reads `setl:        kg       mass settling to bottom of reservoir` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L610)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`, in the order seo4, seo3, boron.

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../reservoir.md).
