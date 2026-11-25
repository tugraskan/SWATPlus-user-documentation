---
description: "This file contains daily channel shading factors, read into `shf_db` by [`shade_factor_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/shade_factor_read.f90#L25-L58).

{% hint style="warning" %}
In [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L371-L387), the `shf_db` lookup runs only when `w_temp(0)%sf_on == 1`. Because [`ch_read_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_temp.f90#L50-L55) loads `temperature.cha` rows into `w_temp(1:)` while `w_temp(0)%sf_on` keeps its built-in default `0`, source reading indicates `shf_db` is not reached on this path at commit `6f515368`.
{% endhint %}"
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file contains daily channel shading factors, read into `shf_db` by [`shade_factor_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/shade_factor_read.f90#L25-L58).

{% hint style="warning" %}
In [`ch_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_temp.f90#L371-L387), the `shf_db` lookup runs only when `w_temp(0)%sf_on == 1`. Because [`ch_read_temp.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/ch_read_temp.f90#L50-L55) loads `temperature.cha` rows into `w_temp(1:)` while `w_temp(0)%sf_on` keeps its built-in default `0`, source reading indicates `shf_db` is not reached on this path at commit `6f515368`.
{% endhint %}

# shade_factor.shf

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [jday](jday.md) | Day of year | integer | day of year | — | — |
| [cha](cha.md) | Channel (reach) identifier for the shading entry | integer | n/a | — | — |
| [value](value.md) | Fraction of incoming shortwave radiation blocked by shading | real | fraction | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
