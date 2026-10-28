---
description: "This file supplies named sets of initial heavy-metal values in HRU soil and plants."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies named sets of initial heavy-metal values in HRU soil and plants.

# hmet_hru.ini

The first two lines contain a title and column headings. For each initial-condition set, enter its name followed by separate soil and plant rows with values for the configured constituents.

## Parameter-set name

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |

## Soil values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [titldum](titldum.md) | Record label | string | n/a | — | — |
| [soil(ihmet)](soil_ihmet.md) | Amount of constituent in soil at start of simulation | real | — | — | — |

## Plant values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [titldum](titldum.md) | Record label | string | n/a | — | — |
| [plt(ihmet)](plt_ihmet.md) | Amount of constituent on plant at start of simulation | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
