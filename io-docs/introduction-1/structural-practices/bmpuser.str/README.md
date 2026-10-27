---
description: This file contains the user Best Management Practice parameters.
---

# bmpuser.str

There are many conservation practices that are not implemented in SWAT+, but for which approximate removal efficiencies have been established. To allow these practices to be included, this generic Best Management Practice (BMP) operation allows fixed removal efficiencies to be specified by constituent.

| Field                    | Description                   | Type    | Unit    | Range     |
| ------------------------ | ----------------------------- | ------- | ------- | --------- |
| [name](name_bmpdb.md)    | ​Name of BMP record           | string  | n/a     | n/a       |
| flag                     | Currently not used            | integer |         |           |
| [sed\_eff](sed_eff.md) | Sediment removal by BMP | real | fraction | 0.0-1.0 |
| [ptlp\_eff](ptlp_eff.md) | ​Particulate P removal by BMP | real | fraction | 0.0-1.0 |
| [solp\_eff](solp_eff.md) | ​Soluble P removal by BMP | real | fraction | 0.0-1.0 |
| [ptln\_eff](ptln_eff.md) | Particulate N removal by BMP | real | fraction | 0.0-1.0 |
| [soln\_eff](soln_eff.md) | Soluble N removal by BMP | real | fraction | 0.0-1.0 |
| [bact\_eff](bact_eff.md) | Bacteria removal by BMP (not applied in SWAT+ main (6f515368)) | real | percent | 0.0-100.0 |
