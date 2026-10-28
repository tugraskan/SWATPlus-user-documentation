---
description: "This file supplies salt-ion inputs from rainfall and dry atmospheric deposition."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies salt-ion inputs from rainfall and dry atmospheric deposition.

SWAT+ looks for `salt_atmo.cli` in the simulation working directory; it is not selected through `file.cio`. See the [cli_read_atmodep_salt.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/cli_read_atmodep_salt.f90#L33) reader.

# salt_atmo.cli

Use the annual, monthly, or yearly values appropriate to each climate station. Each ion row starts with its salt-ion label, followed by the values for that time resolution. Rainfall concentrations and dry-deposition values are separate entries.

## Station

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [station_name](station_name.md) | The identifier of the weather station associated with the annual atmospheric salt deposition record | string | n/a | — | — |

## Annual rainfall concentrations

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [salt_ion](salt_ion.md) | The four-character code naming the salt species for the annual rainfall concentration entry | string | n/a | — | — |
| [rf](rf.md) | The annual average concentration of the salt ion in rainfall | real | — | — | — |

## Annual dry deposition

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [salt_ion](salt_ion.md) | The four-character code naming the salt species for the annual dry deposition entry | string | n/a | — | — |
| [dry](dry.md) | The annual dry deposition flux of the salt ion | real | — | — | — |

## Monthly rainfall concentrations

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [salt_ion](salt_ion.md) | The four-character code naming the salt species for the monthly rainfall concentration entry | string | n/a | — | — |
| [rfmo(imo)](rfmo_imo.md) | The monthly rainfall concentration of the salt ion for month imo | real | — | — | — |

## Monthly dry deposition

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [salt_ion](salt_ion.md) | The four-character code naming the salt species for the monthly dry deposition entry | string | n/a | — | — |
| [drymo(imo)](drymo_imo.md) | The monthly dry deposition flux of the salt ion for month imo | real | — | — | — |

## Yearly rainfall concentrations

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [salt_ion](salt_ion.md) | The four-character code naming the salt species for the yearly rainfall concentration entry | string | n/a | — | — |
| [rfyr(iyr)](rfyr_iyr.md) | The yearly rainfall concentration of the salt ion for year iyr | real | — | — | — |

## Yearly dry deposition

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [salt_ion](salt_ion.md) | The four-character code naming the salt species for the yearly dry deposition entry | string | n/a | — | — |
| [dryyr(iyr)](dryyr_iyr.md) | The yearly dry deposition flux of the salt ion for year iyr | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
