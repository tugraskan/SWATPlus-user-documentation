---
description: "Concentration in reservoir water"
---

# seo4_conc, seo3_conc, born_conc

**Code reference:** `rescs_d(j)%cs(ics)%conc` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L55)).

**Printed header value:** `seo4_conc`, `seo3_conc`, `born_conc` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L94-L96)). The daily legend line reads `conc:        g/m3     concentration in reservoir water` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L617)).

This group holds one value for each constituent slot, `ics = 1` to `cs_db%num_cs`, in the order seo4, seo3, boron.

**Type:** real (format `500e15.4`). **Unit:** g/m3.

[Back to the output table](../reservoir.md).
