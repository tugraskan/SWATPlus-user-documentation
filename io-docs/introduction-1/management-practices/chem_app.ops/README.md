---
description: >-
  This file contains pre-defined fertilizer, manure, and pesticide application
  operations.
---

# chem\_app.ops

| Field                      | Description               |  Type  | Unit | Default | Range |
| -------------------------- | ------------------------- | :----: | :--: | :-----: | :---: |
| [name](name_chem.md)       | Chemical application name | string |  n/a |   n/a   |  n/a  |
| chem\_form\* | Currently not used        | string |      |         |       |
| app\_typ\* | Currently not used        | string |      |         |       |
| [app\_eff](app_eff.md) | Application efficiency | real | n/a | 0. | 0.0-1.0 |
| foliar\_eff                | Currently not used        |  real  |      |         |       |
| [inject\_dp](inject_dp.md)\* | Currently not used | real | mm | 0. |  |
| [surf\_frac](surf_frac.md) | Surface fraction | real | n/a | 0. | 0.0-1.0 |
| drift\_pot                 | Currently not used        |  real  |      |         |       |
| aerial\_unif               | Currently not used        |  real  |      |         |       |

\* Input-file labels marked with an asterisk have different Fortran names: `chem_form` → `chemapp_db(ichemapp)%form`; `app_typ` → `chemapp_db(ichemapp)%op_typ`; `inject_dp` → `chemapp_db(ichemapp)%inject_dep`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/mgt_read_chemapp.f90#L45).
