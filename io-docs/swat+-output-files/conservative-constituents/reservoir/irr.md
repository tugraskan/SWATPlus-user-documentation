---
description: "Mass removed from reservoir for irrigation"
---

# seo4_irrg, seo3_irrg, born_irrg

**Code reference:** `rescs_d(j)%cs(ics)%irrig` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L52)).

**Printed header value:** `seo4_irrg`, `seo3_irrg`, `born_irrg` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L85-L87)). The legend line reads `irr:         kg       mass removed from reservoir for irrigation` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L614)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`, in the order seo4, seo3, boron.

**Type:** real (format `500e15.4`). **Unit:** kg.

[Back to the output table](../reservoir.md).
