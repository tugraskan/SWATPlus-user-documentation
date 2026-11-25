---
description: "This file defines puddling operations used to change soil hydraulic conductivity and sediment concentration in HRU water storage."
---

# puddle.ops

{% hint style="info" %}
An exporter for this file has not been verified in SWAT+ Editor. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines puddling operations used to adjust upper-soil hydraulic conductivity and standing-water sediment concentration during rice-paddy management (`pudl` in `management.sch`, [`mgt_sched.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_sched.f90#L589-L620); or `puddle` in `lum.dtl`, [`actions.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/actions.f90#L959-L998)).

SWAT+ looks for `puddle.ops` in the simulation working directory (loaded in [`proc_db.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/proc_db.f90#L33) via [`mgt_read_puddle.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mgt_read_puddle.f90#L23-L44)); it is not selected through `file.cio`. The first line is a title and the second line contains column headings, followed by one row per named operation.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Puddling operation name | string | n/a | — | — |
| [wet\_hc](wet_hc.md) | Hydraulic conductivity after puddling | real | mm/h | — | — |
| [sed](sed.md) | Sediment concentration after puddling | real | ppm | — | — |
| [orgn](orgn.md) | Organic nitrogen concentration (read but not used in main 6f515368) | real | ppm | — | — |
| [sedp](sedp.md) | Organic phosphorus concentration (read but not used in main 6f515368) | real | ppm | — | — |
| [no3](no3.md) | Nitrate nitrogen concentration (read but not used in main 6f515368) | real | ppm | — | — |
| [solp](solp.md) | Soluble phosphorus concentration (read but not used in main 6f515368) | real | ppm | — | — |
| [nh3](nh3.md) | Ammonia concentration (read but not used in main 6f515368) | real | ppm | — | — |
| [no2](no2.md) | Nitrite concentration (read but not used in main 6f515368) | real | ppm | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
