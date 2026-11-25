---
description: >-
  This file contains pre-defined fertilizer, manure, and pesticide application
  operations.
---

# chem\_app.ops

This file defines pre-defined fertilizer, manure, and pesticide application operations read by [`mgt_read_chemapp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_chemapp.f90#L25-L52).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name_chem.md) | Chemical application name | string | n/a | n/a | n/a |
| [chem\_form](chem_form.md) | Chemical form (e.g., `solid`, `liquid`) (read but not used in main 6f515368) | string | n/a | n/a | n/a |
| [app\_typ](app_typ.md) | Application operation type (e.g., `spread`, `spray`, `inject`, `direct`) (read but not used in main 6f515368) | string | n/a | n/a | n/a |
| [app\_eff](app_eff.md) | Application efficiency (used for pesticides in main 6f515368) | real | n/a | 0. | 0.0-1.0 |
| [foliar\_eff](foliar_eff.md) | Foliar application efficiency (read but not used in main 6f515368) | real | n/a | 0. |  |
| [inject\_dp](inject_dp.md) | Chemical injection depth (read but not used in main 6f515368) | real | mm | 0. |  |
| [surf\_frac](surf_frac.md) | Surface fraction | real | n/a | 0. | 0.0-1.0 |
| [drift\_pot](drift_pot.md) | Spray drift potential (read but not used in main 6f515368) | real | n/a | 0. |  |
| [aerial\_unif](aerial_unif.md) | Aerial application uniformity (read but not used in main 6f515368) | real | n/a | 0. |  |
