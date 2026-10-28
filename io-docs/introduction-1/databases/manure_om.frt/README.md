---
description: "This file supplies the water, carbon, and nutrient composition of named manure types."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies the water, carbon, and nutrient composition of named manure types.

SWAT+ looks for `manure_om.frt` in the simulation working directory; it is not selected through `file.cio`. See the [manure_orgmin_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/manure_orgmin_read.f90#L27) reader.

# manure_om.frt

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [frac_water](frac_water.md) | Mass fraction of the manure that is water | real | — | — | — |
| [fcbn](fcbn.md) | Mass fraction of the fertilizer that is carbon | real | — | — | — |
| [fminn](fminn.md) | Mass fraction of the fertilizer that is mineral nitrogen (sum of NO3 and NH3) | real | — | — | — |
| [fminp](fminp.md) | Mass fraction of the fertilizer that is mineral phosphorus | real | — | — | — |
| [forgn](forgn.md) | Mass fraction of the fertilizer that is organic nitrogen | real | — | — | — |
| [forgp](forgp.md) | Mass fraction of the fertilizer that is organic phosphorus | real | — | — | — |
| [fnh3n](fnh3n.md) | Mass fraction of the mineral nitrogen content that is NH3 | real | — | — | — |
| [description](description.md) | Free-text description of the manure type | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
