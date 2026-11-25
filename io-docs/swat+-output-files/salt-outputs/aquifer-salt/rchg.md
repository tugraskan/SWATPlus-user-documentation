---
description: "Salt mass in groundwater recharge (soil --> aquifer)"
---

# rchg_so4 to rchg_hco3

**Code reference:** `asaltb_d(iaq)%salt(isalt)%rchrg` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L38)).

**Printed header value:** `rchg_so4`, `rchg_ca`, `rchg_mg`, `rchg_na`, `rchg_k`, `rchg_cl`, `rchg_co3`, `rchg_hco3` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aquifer.f90#L51-L58)). The legend line reads `rchg:         kg      salt mass in groundwater recharge         (soil --> aquifer)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L356)).

This is the second group of the row. It holds one value for each of the `cs_db%num_salts` salts. The component is named `rchrg` in the code and `rchg` in the header.

**Type:** real (format `500e18.7`). **Unit:** kg.

[Back to the output table](../aquifer-salt.md).
