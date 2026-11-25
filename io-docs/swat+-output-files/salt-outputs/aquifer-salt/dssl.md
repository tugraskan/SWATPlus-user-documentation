---
description: "Salt mass dissolved from aquifer minerals (mineral --> aquifer)"
---

# dssl_total

**Code reference:** `asaltb_d(iaq)%salt(1)%diss` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/aqu_salt_output.f90#L44)).

**Printed header value:** `dssl_total` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aquifer.f90#L99)). The daily legend line reads `dssl:         kg      salt mass dissolved from aquifer minerals (mineral --> aquifer)` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_salt.f90#L362)).

This is a single value at the end of each row. It is read from the first salt, `salt(1)`, and is not repeated for the other salts. The component is named `diss` in the code, `dssl_total` in the column-name row, and `dssl` in the legend.

**Type:** real (format `500e18.7`). **Unit:** kg.

[Back to the output table](../aquifer-salt.md).
