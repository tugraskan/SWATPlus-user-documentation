---
description: >-
  This file summarizes the main land use information and references several
  other files that specify the details.
---

# landuse.lum



| Field                         | Description                                   |  Type  |
| ----------------------------- | --------------------------------------------- | :----: |
| [name](name.md)               | Name of the land use and management record    | string |
| [cal\_group](cal_grp.md) | Calibration group | string |
| [plnt\_com](plnt_com.md)\* | Pointer to the plant community file | string |
| [mgt](mgt.md)\* | Pointer to the management schedule file       | string |
| [cn2](cn2.md)\* | Pointer to the Curve Number database          | string |
| [cons\_prac](cons_prac.md)    | Pointer to the conservation practice database | string |
| [urban](urb_ro.md)\* | Pointer to the urban database                 | string |
| [urb\_ro](urb_ro-1.md)        | Urban runoff simulation option                | string |
| [ov\_mann](ov_mann.md)\* | Pointer to the overland Manning's n database  | string |
| [tile](tile.md)\* | Pointer to the tile drain file                | string |
| [sep](sep.md)\* | Pointer to the septic file                    | string |
| [vfs](vfs.md)\* | Pointer to the filter strip file              | string |
| [grww](grww.md)\* | Pointer to the grassed waterway file          | string |
| [bmp](bmp.md)\* | Pointer to the user BMP file                  | string |

\* Input-file labels marked with an asterisk have different Fortran names: `plnt_com` → `lum(ilu)%plant_cov`; `mgt` → `lum(ilu)%mgt_ops`; `cn2` → `lum(ilu)%cn_lu`; `urban` → `lum(ilu)%urb_lu`; `ov_mann` → `lum(ilu)%ovn`; `tile` → `lum(ilu)%tiledrain`; `sep` → `lum(ilu)%septic`; `vfs` → `lum(ilu)%fstrip`; `grww` → `lum(ilu)%grassww`; `bmp` → `lum(ilu)%bmpuser`. [Reader](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/landuse_read.f90#L56).
