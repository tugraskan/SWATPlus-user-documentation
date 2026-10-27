---
description: >-
  This file summarizes the main channel information and references several other
  files that specify the details.
---

# channel-lte.cha

| Field                       | Description                                         |   Type  |
| --------------------------- | --------------------------------------------------- | :-----: |
| [id](id-channel-lte.cha.md)\* | ID of the channel                                   | integer |
| [name](name.md)             | Name of the channel                                 |  string |
| [cha\_ini](cha_ini.md)\* | Pointer to the channel initialization file | string |
| [cha\_hyd](cha_hyd.md)\* | Pointer to the channel hydrology and sediment file | string |
| cha\_sed\* | Currently not used | string |
| [cha\_nut](cha_nut.md)\* | Pointer to the channel nutrient file | string |

\* Input-file labels marked with an asterisk have different Fortran names: `id` → `k`; `cha_ini` → `sd_dat(i)%initc`; `cha_hyd` → `sd_dat(i)%hydc`; `cha_sed` → `sd_dat(i)%sedc`; `cha_nut` → `sd_dat(i)%nutc`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/sd_channel_read.f90#L222).
