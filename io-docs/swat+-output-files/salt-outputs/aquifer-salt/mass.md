---
description: "Salt mass stored in aquifer"
---

# mass_so4 to mass_hco3

**Code reference:** `asaltb_d(iaq)%salt(isalt)%mass` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L42)).

**Printed header value:** `mass_so4`, `mass_ca`, `mass_mg`, `mass_na`, `mass_k`, `mass_cl`, `mass_co3`, `mass_hco3` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aquifer.f90#L83-L90)). The daily legend line reads `mass:         kg      salt mass stored in aquifer` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L360)).

This is the sixth group of the row. It holds one value for each of the `cs_db%num_salts` salts.

**Type:** real (format `500e18.7`). **Unit:** kg.

[Back to the output table](../aquifer-salt.md).
