---
description: "Salt concentration in groundwater"
---

# conc_so4 to conc_hco3

**Code reference:** `asaltb_d(iaq)%salt(isalt)%conc` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L43)).

**Printed header value:** `conc_so4`, `conc_ca`, `conc_mg`, `conc_na`, `conc_k`, `conc_cl`, `conc_co3`, `conc_hco3` ([header names](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aquifer.f90#L91-L98)). The daily legend line reads `conc:         g/m3    salt concentration in groundwater` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L361)).

This is the seventh group of the row. It holds one value for each of the `cs_db%num_salts` salts.

**Type:** real (format `500e18.7`). **Unit:** g/m3.

[Back to the output table](../aquifer-salt.md).
