---
description: "This file supplies named sets of initial salt-ion concentrations in channel water."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named sets of initial salt-ion concentrations in channel water.

SWAT+ looks for `salt_channel.ini` in the simulation working directory; it is not selected through `file.cio`. See the [`salt_cha_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_cha_read.f90#L27-L57) reader.

# salt\_channel.ini

The first two lines contain a title and column headings ([`salt_cha_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_cha_read.f90#L28-L30)). Each following row contains the fields below, in this order.

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |
| [conc](conc.md) | Initial salt ion concentrations at the start of the simulation | real | g/m^3 (mg/L) | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
