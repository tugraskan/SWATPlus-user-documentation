---
description: "This file links each channel to its initial-condition, hydrology, sediment, and nutrient parameter sets."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links each channel to its initial-condition, hydrology, sediment, and nutrient parameter sets.

# channel.cha

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Record number | integer | n/a | — | — |
| [name](name.md) | Record name | string | n/a | — | — |
| [init](init.md) | Name of the initial channel record in initial.cha that this channel data references | string | n/a | — | — |
| [hyd](hyd.md) | Name of the hydrology record in hydrology.cha that provides hydrology inputs for this channel | string | n/a | — | — |
| [sed](sed.md) | Name of the sediment record in sediment.cha that provides sediment inputs for this channel | string | n/a | — | — |
| [nut](nut.md) | Name of the nutrient record in nutrients.cha that provides nutrient inputs for this channel | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
