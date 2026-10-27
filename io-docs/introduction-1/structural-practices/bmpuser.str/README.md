---
description: This file contains the user Best Management Practice parameters.
---

# bmpuser.str

There are many conservation practices that are not implemented in SWAT+, but for which approximate removal efficiencies have been established. To allow these practices to be included, this generic Best Management Practice (BMP) operation allows fixed removal efficiencies to be specified by constituent.

| Field                    | Description                   | Type    | Unit    | Range     |
| ------------------------ | ----------------------------- | ------- | ------- | --------- |
| [name](name_bmpdb.md)    | ​Name of BMP record           | string  | n/a     | n/a       |
| flag\* | Currently not used            | integer |         |           |
| [sed\_eff](sed_eff.md)\* | Sediment removal by BMP | real | fraction | 0.0-1.0 |
| [ptlp\_eff](ptlp_eff.md)\* | ​Particulate P removal by BMP | real | fraction | 0.0-1.0 |
| [solp\_eff](solp_eff.md)\* | ​Soluble P removal by BMP | real | fraction | 0.0-1.0 |
| [ptln\_eff](ptln_eff.md)\* | Particulate N removal by BMP | real | fraction | 0.0-1.0 |
| [soln\_eff](soln_eff.md)\* | Soluble N removal by BMP | real | fraction | 0.0-1.0 |
| [bact\_eff](bact_eff.md)\* | Bacteria removal by BMP (not applied in SWAT+ main (6f515368)) | real | percent | 0.0-100.0 |

\* Input-file labels marked with an asterisk have different Fortran names: `flag` → `bmpuser_db(ibmpop)%bmp_flag`; `sed_eff` → `bmpuser_db(ibmpop)%bmp_sed`; `ptlp_eff` → `bmpuser_db(ibmpop)%bmp_pp`; `solp_eff` → `bmpuser_db(ibmpop)%bmp_sp`; `ptln_eff` → `bmpuser_db(ibmpop)%bmp_pn`; `soln_eff` → `bmpuser_db(ibmpop)%bmp_sn`; `bact_eff` → `bmpuser_db(ibmpop)%bmp_bac`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/scen_read_bmpuser.f90#L43).
