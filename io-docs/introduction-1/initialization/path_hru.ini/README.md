---
description: "This file supplies named sets of initial pathogen values in HRU soil and plants."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named sets of initial pathogen values in HRU soil and plants.

# path_hru.ini

After the title and column headings, enter each initial-set name followed by a labeled row containing the soil and plant values for the configured pathogens.

## Parameter-set name

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [titldum](titldum.md) | Record label | string | n/a | — | — |
| [soil](soil.md) | Initial soil-compartment value for each pathogen | real | — | — | — |
| [plt](plt.md) | Initial plant-compartment value for each pathogen | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
