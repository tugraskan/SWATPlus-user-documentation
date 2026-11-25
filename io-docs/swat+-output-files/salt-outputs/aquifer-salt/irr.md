---
description: "Salt mass in groundwater irrigation (aquifer --> soil)"
---

# irr_so4 to irr_hco3

**Code reference:** `asaltb_d(iaq)%salt(isalt)%irr` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L40)).

**Printed header value:** `irr_so4`, `irr_ca`, `irr_mg`, `irr_na`, `irr_k`, `irr_cl`, `irr_co3`, `irr_hco3` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aquifer.f90#L67-L74)). The legend line reads `irr:          kg      salt mass in groundwater irrigation       (aquifer --> soil)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L358)).

This is the fourth group of the row. It holds one value for each of the `cs_db%num_salts` salts.

**Type:** real (format `500e18.7`). **Unit:** kg.

[Back to the output table](../aquifer-salt.md).
