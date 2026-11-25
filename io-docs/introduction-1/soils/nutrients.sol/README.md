---
description: This file specifies the initial soil nutrient contents.
---

# nutrients.sol

This file specifies initial soil nutrient concentrations and humus C:N and C:P ratios read by [`solt_db_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/solt_db_read.f90#L47).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name-nutrients.sol.md) | Name of the soil nutrient record | string | n/a |  |  |
| [exp\_co](exp_co.md) | Depth coefficient to adjust nutrient concentrations for depth | real | 1/mm |  |  |
| [lab\_p](lab_p.md) | Labile P in soil surface | real | ppm |  |  |
| [nitrate](nitrate.md) | Nitrate N in soil surface | real | ppm |  |  |
| [fr\_hum\_act](fr_hum_act.md) | Fraction of soil humus that is active | real | fraction |  |  |
| [hum\_c\_n](hum_c_n.md) | Humus C:N ratio | real | ratio |  |  |
| [hum\_c\_p](hum_c_p.md) | Humus C:P ratio | real | ratio |  |  |
| [inorgp](inorgp.md) | Inorganic P in soil surface (not used) | real | ppm |  |  |
| [watersol\_p](watersol_p.md) | Water-soluble P in soil surface (not used) | real | ppm |  |  |
| [h3a\_p](h3a_p.md) | H3A extractable P in soil surface (not used) | real | ppm |  |  |
| [mehlich\_p](mehlich_p.md) | Mehlich extractable P in soil surface (not used) | real | ppm |  |  |
| [bray\_strong\_p](bray_strong_p.md) | Bray strong-extractable P in soil surface (not used) | real | ppm |  |  |
