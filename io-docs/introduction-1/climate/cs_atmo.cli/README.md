---
description: "This file supplies general-constituent inputs from rainfall and dry atmospheric deposition."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies general-constituent inputs from rainfall and dry atmospheric deposition.

SWAT+ looks for `cs_atmo.cli` in the simulation working directory; it is not selected through `file.cio`. See the [cli_read_atmodep_cs.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_read_atmodep_cs.f90#L32) reader.

# cs_atmo.cli

Use the annual, monthly, or yearly values appropriate to each climate station. The station name identifies the station block. Rainfall concentrations and dry-deposition values are separate entries, with repeated values for the configured constituents and periods.

## Station

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [station_name](station_name.md) | Station identifier for the annual timestep record (station_name) | real | — | — | — |

## Annual rainfall concentrations

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [rf](rf.md) | Annual rainfall concentration of the constituent in rainfall (mg/L) | real | — | — | — |

## Annual dry deposition

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dry](dry.md) | Annual dry deposition flux of the constituent (kg/ha/yr), divided by 365 to obtain a daily rate | real | — | — | — |

## Monthly rainfall concentrations

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [rfmo(imo)](rfmo_imo.md) | Monthly rainfall concentration of the constituent for month imo | real | — | — | — |

## Monthly dry deposition

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [drymo(imo)](drymo_imo.md) | Monthly dry deposition flux of the constituent for month imo | real | — | — | — |

## Yearly rainfall concentrations

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [rfyr(iyr)](rfyr_iyr.md) | Yearly rainfall concentration of the constituent for year iyr | real | — | — | — |

## Yearly dry deposition

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [dryyr(iyr)](dryyr_iyr.md) | Yearly dry deposition flux of the constituent for year iyr, divided by 365 to obtain a daily rate | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
