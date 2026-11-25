---
description: "Mass added to reservoir via fertilizer"
---

# seo4_fert, seo3_fert, born_fert

**Code reference:** `rescs_d(j)%cs(ics)%fert` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L51)).

**Printed header value:** `seo4_fert`, `seo3_fert`, `born_fert` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L82-L84)). The legend line reads `fert:        kg       mass added to reservoir via fertilizer` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L613)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`, in the order seo4, seo3, boron. It is written between the `prod` and `irr` groups.

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../reservoir.md).
