---
description: "Salt mass in groundwater seepage (aquifer --> deep)"
---

# seep_so4 to seep_hco3

**Code reference:** `asaltb_d(iaq)%salt(isalt)%seep` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L39)).

**Printed header value:** `seep_so4`, `seep_ca`, `seep_mg`, `seep_na`, `seep_k`, `seep_cl`, `seep_co3`, `seep_hco3` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aquifer.f90#L59-L66)). The legend line reads `seep:         kg      salt mass in groundwater seepage          (aquifer --> deep)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L357)).

This is the third group of the row. It holds one value for each of the `cs_db%num_salts` salts.

**Type:** real (format `500e18.7`). **Unit:** kg.

[Back to the output table](../aquifer-salt.md).
