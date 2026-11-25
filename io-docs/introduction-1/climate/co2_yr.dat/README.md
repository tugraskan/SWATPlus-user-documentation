---
description: "This file supplies atmospheric carbon dioxide concentrations for individual years."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies atmospheric carbon dioxide concentrations for individual years.

SWAT+ looks for `co2_yr.dat` in the simulation working directory; it is not selected through `file.cio`. See the [co2_read.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/co2_read.f90#L45) reader.

# co2_yr.dat

The file contains a title, the number of annual entries, column headings, and one row per annual entry. Each annual row contains the year and its CO2 concentration.

## Number of annual entries

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [yrs](yrs.md) | Total number of annual CO2 records (integer) that follow in this file | integer | n/a | — | — |

## Annual concentrations

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [iyr](iyr.md) | Simulation year (integer) identifying the start of the year for which the CO2 value is defined | integer | n/a | — | — |
| [co2](co2.md) | Atmospheric CO2 concentration (real) in parts per million (ppm) for the year given by iyr | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.

The reader opens the literal filename co2_yr.dat. Supply a title, a record count, a header and then consecutive annual rows in ascending order. With no entries SWAT+ uses the basin CO₂ parameter. Before the first year it uses the first concentration, and after the last it uses the last concentration. See [co2_read.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/co2_read.f90#L40-L109).
