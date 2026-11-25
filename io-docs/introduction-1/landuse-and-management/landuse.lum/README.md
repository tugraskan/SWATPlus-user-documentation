---
description: >-
  This file summarizes the main land use information and references several
  other files that specify the details.
---

# landuse.lum

This file defines land use and management records read by [`landuse_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L35-L58). Enter `"null"` to disable an optional foreign-key pointer; any non-`"null"` pointer that does not match its target file is logged to `diagnostics.out` ([`landuse_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/landuse_read.f90#L143-L169)).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Name of the land use and management record | string | n/a | n/a | n/a |
| [cal\_group](cal_grp.md) | Calibration group | string | n/a | n/a | n/a |
| [plnt\_com](plnt_com.md) | Pointer to the plant community file | string | n/a | n/a | n/a |
| [mgt](mgt.md) | Pointer to the management schedule file | string | n/a | n/a | n/a |
| [cn2](cn2.md) | Pointer to the Curve Number database | string | n/a | n/a | n/a |
| [cons\_prac](cons_prac.md) | Pointer to the conservation practice database | string | n/a | n/a | n/a |
| [urban](urb_ro.md) | Pointer to the urban database | string | n/a | n/a | n/a |
| [urb\_ro](urb_ro-1.md) | Urban runoff simulation option | string | n/a | n/a | n/a |
| [ov\_mann](ov_mann.md) | Pointer to the overland Manning's n database | string | n/a | n/a | n/a |
| [tile](tile.md) | Pointer to the tile drain file | string | n/a | n/a | n/a |
| [sep](sep.md) | Pointer to the septic file | string | n/a | n/a | n/a |
| [vfs](vfs.md) | Pointer to the filter strip file | string | n/a | n/a | n/a |
| [grww](grww.md) | Pointer to the grassed waterway file | string | n/a | n/a | n/a |
| [bmp](bmp.md) | Pointer to the user BMP file | string | n/a | n/a | n/a |
