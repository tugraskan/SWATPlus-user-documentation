---
description: "This file supplies named sets of initial pathogen values in water and benthic compartments."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named sets of initial pathogen values in water and benthic compartments.

# path_water.ini

After the title and column headings, enter each initial-set name followed by a labeled row containing the water and benthic values for the configured pathogens.

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [path_init_name(ipathi)](path_init_name_ipathi.md) | Name identifying this initial pathogen set | string | n/a | — | — |

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [titldum](titldum.md) | Record label | string | n/a | — | — |
| [water](water.md) | Initial water-compartment value for each pathogen | real | — | — | — |
| [benthic](benthic.md) | Initial benthic-compartment value for each pathogen | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
