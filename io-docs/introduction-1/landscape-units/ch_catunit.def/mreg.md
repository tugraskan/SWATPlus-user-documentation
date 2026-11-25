---
description: "Number of regions"
---

# mreg

**Code reference:** `mreg` -> `db_mx%cha_reg` ([declaration](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L19), [read](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L39), [stored](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L77)).

Total number of channel cataloging units defined in [`ch_catunit.def`](README.md) (`integer`, dimensionless, default `0`). In [`ch_read_elements.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_elements.f90#L77), `mreg` is written to `db_mx%cha_reg` (overwritten at line 121 if [`ch_reg.def`](../ch_reg.def/README.md) exists); `db_mx%cha_reg` is used as a loop bound in [`calsoft_sed.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/calsoft_sed.f90#L42) and checked in [`ch_read_orders_cal.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_orders_cal.f90#L126).
