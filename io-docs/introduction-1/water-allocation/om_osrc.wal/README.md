---
description: "This file supplies named organic/mineral component values for outside water sources."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the tables are based on the SWAT+ Fortran source (`6f515368`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In [`om_osrc_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_osrc_read.f90#L30-L45), the outer `do ... end do` read loop lacks an `exit` statement after reading `imax` records.
{% endhint %}

This file supplies named organic/mineral component values for outside water sources.

SWAT+ looks for `om_osrc.wal` in the simulation working directory; it is not selected through `file.cio`. See the [`om_osrc_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/om_osrc_read.f90#L31) reader.

# om_osrc.wal

The file contains a title, the entry count, column headings, and the corresponding data rows shown below.

## Number of records

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Input values

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [om_osrc_name](om_osrc_name.md) | Name identifying this component-value record | string | n/a | — | — |
| [flo](flo.md) | Daily available water volume for this outside source record | real | m^3/day | 0. | — |
| [sed](sed.md) | Sediment concentration | real | ppm (mg/L) | 0. | — |
| [orgn](orgn.md) | Organic-nitrogen concentration | real | ppm (mg/L) | 0. | — |
| [sedp](sedp.md) | Organic-phosphorus concentration | real | ppm (mg/L) | 0. | — |
| [no3](no3.md) | Nitrate-nitrogen concentration | real | ppm (mg/L) | 0. | — |
| [solp](solp.md) | Soluble-phosphorus concentration | real | ppm (mg/L) | 0. | — |
| [chla](chla.md) | Chlorophyll-a concentration | real | ppm (mg/L) | 0. | — |
| [nh3](nh3.md) | Ammonia-nitrogen concentration | real | ppm (mg/L) | 0. | — |
| [no2](no2.md) | Nitrite-nitrogen concentration | real | ppm (mg/L) | 0. | — |
| [cbod](cbod.md) | Carbonaceous biological oxygen demand concentration | real | ppm (mg/L) | 0. | — |
| [dox](dox.md) | Dissolved-oxygen concentration | real | ppm (mg/L) | 0. | — |
| [san](san.md) | Sand concentration | real | ppm (mg/L) | 0. | — |
| [sil](sil.md) | Silt concentration | real | ppm (mg/L) | 0. | — |
| [cla](cla.md) | Clay concentration | real | ppm (mg/L) | 0. | — |
| [sag](sag.md) | Small-aggregate concentration | real | ppm (mg/L) | 0. | — |
| [lag](lag.md) | Large-aggregate concentration | real | ppm (mg/L) | 0. | — |
| [grv](grv.md) | Gravel concentration | real | ppm (mg/L) | 0. | — |
| [temp](temp.md) | Water temperature | real | deg C | 0. | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
