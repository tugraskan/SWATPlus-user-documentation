---
description: "Volume of water stored in reservoir"
---

# vol_m3

**Code reference:** `rescs_d(j)%cs(1)%volm` ([writer](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_output.f90#L56)).

**Printed header value:** `vol_m3` ([header](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/res_cs_module.f90#L97)). The daily legend line reads `vol_m3:      m3       volume of water stored in reservoir` ([legend](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/header_const.f90#L618)).

This is a single value at the end of each row. It is taken from the first constituent slot, `cs(1)`, and is not repeated for the other constituents.

**Type:** real (format `500e15.4`). **Unit:** m3.

[Back to the output table](../reservoir.md).
