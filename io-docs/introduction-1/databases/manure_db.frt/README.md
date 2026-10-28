---
description: "This file links named manure types to their constituent composition records."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file links named manure types to their constituent composition records.

SWAT+ looks for `manure_db.frt` in the simulation working directory; it is not selected through `file.cio`. See the [manure_db_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/manure_db_read.f90#L27) reader.

# manure_db.frt

The first two lines contain a title and column headings. Each following row contains the fields below, in this order.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [org_min](org_min.md) | Identifier matching this manure type against the organic/mineral constituent database entry that supplies sediment | string | n/a | — | — |
| [pests](pests.md) | Identifier matching this manure type against the pesticide database entry supplying pesticide concentrations | string | n/a | — | — |
| [paths](paths.md) | Identifier matching this manure type against the pathogen database entry supplying pathogen counts | string | n/a | — | — |
| [hmets](hmets.md) | Identifier matching this manure type against the heavy-metal database entry supplying heavy-metal concentrations | string | n/a | — | — |
| [salts](salts.md) | Identifier matching this manure type against the salt database entry supplying salt-ion concentrations | string | n/a | — | — |
| [constit](constit.md) | Identifier matching this manure type against the other-constituent database entry supplying additional constituent concentrations | string | n/a | — | — |
| [descrip](descrip.md) | Free-text description of the manure type | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
