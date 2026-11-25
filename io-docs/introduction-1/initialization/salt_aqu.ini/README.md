---
description: "This file supplies named sets of initial salt concentrations and mineral percentages for aquifers."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named sets of initial salt concentrations and mineral percentages for aquifers.

SWAT+ looks for `salt_aqu.ini` in the simulation working directory; it is not selected through `file.cio`. See the [`salt_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aqu_read.f90#L23-L66) reader.

# salt\_aqu.ini

The first **4 lines** contain a title and three header lines ([`salt_aqu_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/salt_aqu_read.f90#L24-L30)). Each following row contains the fields below, in this order: `name`, `cs_db%num_salts` dissolved ion concentrations (`conc`), and `5` salt mineral percentages (`frac`).

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name | string | n/a | — | — |
| [conc](conc.md) | Salt ion concentrations at the start of the simulation | real | g/m^3 (mg/L) | — | — |
| [frac](frac.md) | Salt mineral percentages at the start of the simulation (labeled `frac`, but treated as `%` `0–100`) | real | % | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
