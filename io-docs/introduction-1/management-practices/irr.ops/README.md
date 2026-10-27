---
description: This file contains pre-defined irrigation operations.
---

# irr.ops

| Field                         | Description                                             | Type   | Unit     | Default | Range   |
| ----------------------------- | ------------------------------------------------------- | ------ | -------- | ------- | ------- |
| [name](name_irr.md)           | Irrigation operation name                               | string | n/a      | n/a     | n/a     |
| [amt_mm](irr_amt.md)          | Irrigation application amount                           | real   | mm       | 0.0     |         |
| [eff_frac](irr_eff.md)\* | Irrigation in-field efficiency                          | real   | fraction | 0.0     | 0.0-1.0 |
| [sumq_frac](surq_rto.md)\* | Surface runoff ratio                                    | real   | fraction | 0.0     | 0.0-1.0 |
| [dep_sub](irr_dep.md)\* | Currently not used in SWAT+ main (6f515368)                     | real   | mm       | 0.0     |         |
| [salt_ppm](irr_salt.md)\* | Currently not used in SWAT+ main (6f515368)                     | real   | mg/kg    | 0.0     |         |
| [no3_ppm](irr_no3n.md)\* | Concentration of nitrate in irrigation water            | real   | mg/kg    | 0.0     |         |
| [po4_ppm](irr_po4.md)\* | Currently not used in SWAT+ main (6f515368)                     | real   | mg/kg    | 0.0     |         |

\* Input-file labels marked with an asterisk have different Fortran names: `eff_frac` → `irrop_db(irr_op)%eff`; `sumq_frac` → `irrop_db(irr_op)%surq`; `dep_sub` → `irrop_db(irr_op)%dep_mm`; `salt_ppm` → `irrop_db(irr_op)%salt`; `no3_ppm` → `irrop_db(irr_op)%no3`; `po4_ppm` → `irrop_db(irr_op)%po4`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_read_irrops.f90#L48).
