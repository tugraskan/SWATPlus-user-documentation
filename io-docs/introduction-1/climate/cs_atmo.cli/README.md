---
description: "This file supplies general-constituent inputs from rainfall and dry atmospheric deposition."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies general-constituent inputs from rainfall and dry atmospheric deposition.

SWAT+ looks for `cs_atmo.cli` in the simulation working directory; it is not selected through `file.cio`. See the [cli_read_atmodep_cs.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_read_atmodep_cs.f90#L32) reader.

# cs_atmo.cli

Use the average annual, monthly, or yearly values appropriate to each climate station. The station name identifies the station block. Rainfall concentrations and dry-deposition values are separate entries, with repeated values for the configured constituents and periods.

## Station

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [station_name](station_name.md) | Numeric station token in each station block | real | — | — | — |

## Average annual rainfall concentrations

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [rf](rf.md) | Annual rainfall concentration of the constituent in rainfall (mg/L) | real | mg/L | — | — |

## Average annual dry deposition

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [dry](dry.md) | Annual dry deposition flux of the constituent (kg/ha/yr), divided by 365 to obtain a daily rate | real | kg/ha | — | — |

## Monthly rainfall concentrations

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [rfmo(imo)](rfmo_imo.md) | Monthly rainfall concentration of the constituent for month imo | real | mg/L | — | — |

## Monthly dry deposition

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [drymo(imo)](drymo_imo.md) | Monthly dry deposition amount of the constituent for month imo | real | kg/ha | — | — |

## Yearly rainfall concentrations

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [rfyr(iyr)](rfyr_iyr.md) | Yearly rainfall concentration of the constituent for year iyr | real | mg/L | — | — |

## Yearly dry deposition

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [dryyr(iyr)](dryyr_iyr.md) | Yearly dry deposition amount of the constituent for year iyr, divided by 365 to obtain a daily rate | real | kg/ha | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.

The reader skips 3 leading records and gets station count, timestep and period count from [atmo.cli](../atmo.cli/README.md). Supply stations in the same order as in that file. Each station block contains the station token, all wet records and then all dry records, in configured species order. Monthly and yearly rows each supply one value per period. See [cli_read_atmodep_cs.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_read_atmodep_cs.f90#L24-L93).
