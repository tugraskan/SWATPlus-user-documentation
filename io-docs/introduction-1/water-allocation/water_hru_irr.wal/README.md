---
description: "This file groups irrigation HRUs and assigns their irrigation-demand decision tables."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the tables are based on the SWAT+ Fortran source (`6f515368`). A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

{% hint style="warning" %}
In [`water_hru_irr_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_hru_irr_read.f90#L28-L50), the outer `do ... end do` loop lacks an `exit` statement after reading `imax` records.
{% endhint %}

This file groups irrigation HRUs and assigns their irrigation-demand decision tables.

SWAT+ looks for `water_hru_irr.wal` in the simulation working directory; it is not selected through `file.cio`. See the [`water_hru_irr_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/water_hru_irr_read.f90#L29) reader.

# water_hru_irr.wal

After the title, group count, and headings, enter an irrigation-group name and HRU count. Follow each group with one HRU identifier and demand decision-table name per member.

## Irrigation-group count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [imax](imax.md) | Number of irrigation groups | integer | n/a | — | — |

## Irrigation groups

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Irrigation-group name | string | n/a | — | — |
| [hrus](hrus.md) | Number of HRUs in the irrigation group | integer | n/a | 0 | — |

## Group members

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [hru_num(j)](hru_num_j.md) | HRU number for the j-th member | integer | n/a | — | — |
| [dtbl_lum(j)](dtbl_lum_j.md) | Landuse-management decision-table name for the j-th HRU | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
