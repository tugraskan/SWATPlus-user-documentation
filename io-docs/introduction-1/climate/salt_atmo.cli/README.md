---
description: "This file supplies salt-ion inputs from rainfall and dry atmospheric deposition."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies salt-ion inputs from rainfall and dry atmospheric deposition.

SWAT+ looks for `salt_atmo.cli` in the simulation working directory; it is not selected through `file.cio`. See the [cli_read_atmodep_salt.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_read_atmodep_salt.f90#L33) reader.

# salt_atmo.cli

Use the annual, monthly, or yearly values appropriate to each climate station. Each ion row starts with its salt-ion label, followed by the values for that time resolution. Rainfall concentrations and dry-deposition values are separate entries.

## Station

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [station_name](station_name.md) | Station label read at the start of each block | string | n/a | — | — |

## Average annual rainfall concentrations

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [salt_ion](salt_ion.md) | The four-character code printed for the salt species for the annual rainfall concentration entry | string | n/a | — | — |
| [rf](rf.md) | The annual average concentration of the salt ion in rainfall | real | mg/L | — | — |

## Average annual dry deposition

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [salt_ion](salt_ion.md) | The four-character code printed for the salt species for the annual dry deposition entry | string | n/a | — | — |
| [dry](dry.md) | The annual dry deposition flux of the salt ion | real | kg/ha | — | — |

## Monthly rainfall concentrations

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [salt_ion](salt_ion.md) | The four-character code printed for the salt species for the monthly rainfall concentration entry | string | n/a | — | — |
| [rfmo(imo)](rfmo_imo.md) | The monthly rainfall concentration of the salt ion for month imo | real | mg/L | — | — |

## Monthly dry deposition

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [salt_ion](salt_ion.md) | The four-character code printed for the salt species for the monthly dry deposition entry | string | n/a | — | — |
| [drymo(imo)](drymo_imo.md) | The monthly dry deposition flux of the salt ion for month imo | real | kg/ha | — | — |

## Yearly rainfall concentrations

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [salt_ion](salt_ion.md) | The four-character code printed for the salt species for the yearly rainfall concentration entry | string | n/a | — | — |
| [rfyr(iyr)](rfyr_iyr.md) | The yearly rainfall concentration of the salt ion for year iyr | real | mg/L | — | — |

## Yearly dry deposition

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [salt_ion](salt_ion.md) | The four-character code printed for the salt species for the yearly dry deposition entry | string | n/a | — | — |
| [dryyr(iyr)](dryyr_iyr.md) | The yearly dry deposition flux of the salt ion for year iyr | real | kg/ha | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.

The reader skips 6 leading records and gets station count, timestep and period count from [atmo.cli](../atmo.cli/README.md). Supply stations in the same order as in that file. Each station block contains the station token, all wet records and then all dry records, in configured species order. Monthly and yearly rows each supply one value per period. See [cli_read_atmodep_salt.f90](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/cli_read_atmodep_salt.f90#L24-L93).
