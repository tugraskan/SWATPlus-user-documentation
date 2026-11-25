---
description: This file contains pre-defined irrigation operations.
---

# irr.ops

This file defines pre-defined irrigation operations read by [`mgt_read_irrops.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_irrops.f90#L28-L58).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name_irr.md) | Irrigation operation name | string | n/a | n/a | n/a |
| [amt\_mm](irr_amt.md) | Irrigation application amount | real | mm | 0.0 |  |
| [eff\_frac](irr_eff.md) | Irrigation in-field efficiency | real | fraction | 0.0 | 0.0-1.0 |
| [sumq\_frac](surq_rto.md) | Surface runoff ratio | real | fraction | 0.0 | 0.0-1.0 |
| [dep\_sub](irr_dep.md) | Depth of subsurface-irrigation application (read but not applied in main 6f515368) | real | mm | 0.0 |  |
| [salt\_ppm](irr_salt.md) | Total salt concentration in irrigation water (copied to irrigation state but not used in calculations in main 6f515368) | real | mg/kg | 0.0 |  |
| [no3\_ppm](irr_no3n.md) | Concentration of nitrate in irrigation water | real | mg/kg | 0.0 |  |
| [po4\_ppm](irr_po4.md) | Phosphate concentration in irrigation water (read but not applied in main 6f515368) | real | mg/kg | 0.0 |  |
