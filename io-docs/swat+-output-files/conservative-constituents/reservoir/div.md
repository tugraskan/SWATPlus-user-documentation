---
description: "Mass removed (-) or added (+) via diversion"
---

# seo4_div, seo3_div, born_div

**Code reference:** `rescs_d(j)%cs(ics)%div` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L53)).

**Printed header value:** `seo4_div`, `seo3_div`, `born_div` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L88-L90)). The legend line reads `div:         kg       mass removed (-) or added (+) via diversion` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L615)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`, in the order seo4, seo3, boron.

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../reservoir.md).
