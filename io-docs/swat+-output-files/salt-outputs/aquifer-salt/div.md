---
description: "Salt mass removed (-) or added (+) via diversion"
---

# div_so4 to div_hco3

**Code reference:** `asaltb_d(iaq)%salt(isalt)%div` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L41)).

**Printed header value:** `div_so4`, `div_ca`, `div_mg`, `div_na`, `div_k`, `div_cl`, `div_co3`, `div_hco3` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aquifer.f90#L75-L82)). The legend line reads `div:          kg      salt mass removed (-) or added (+) via diversion` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L359)).

This is the fifth group of the row. It holds one value for each of the `cs_db%num_salts` salts.

**Type:** real (format `500e18.7`). **Unit:** kg.

[Back to the output table](../aquifer-salt.md).
