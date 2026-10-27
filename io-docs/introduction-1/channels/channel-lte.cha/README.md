---
description: >-
  This file summarizes the main channel information and references several other
  files that specify the details.
---

# channel-lte.cha

| Field                       | Description                                         |   Type  |
| --------------------------- | --------------------------------------------------- | :-----: |
| [id](id-channel-lte.cha.md) | ID of the channel                                   | integer |
| [name](name.md)             | Name of the channel                                 |  string |
| [cha\_ini](cha_ini.md) | Pointer to the channel initialization file | string |
| [cha\_hyd](cha_hyd.md) | Pointer to the channel hydrology and sediment file | string |
| cha\_sed | Currently not used | string |
| [cha\_nut](cha_nut.md) | Pointer to the channel nutrient file | string |

## Names used in the code

These input-file fields have different internal names in the Fortran code:

| Input-file name | Fortran name |
| --- | --- |
| `cha_ini` | `initc` |
| `cha_hyd` | `hydc` |
| `cha_sed` | `sedc` |
| `cha_nut` | `nutc` |
