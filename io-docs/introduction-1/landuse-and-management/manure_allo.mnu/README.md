---
description: "This file defines manure sources, receiving objects, and the rules used to allocate manure between them."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines manure sources, receiving objects, and the rules used to allocate manure between them.

SWAT+ looks for `manure_allo.mnu` in the simulation working directory; it is not selected through `file.cio`. See the [manure_allocation_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/manure_allocation_read.f90#L39) reader.

# manure_allo.mnu

After the title and allocation count, enter each allocation-object block. A block has its own object headings and definition row, source headings and source rows, then receiving-object headings and receiver rows. The definition gives the number of source and receiving rows.

## Allocation count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Allocation objects

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [rule_typ](rule_typ.md) | Allocation rule type for the manure allocation object | string | n/a | — | — |
| [src_obs](src_obs.md) | Number of source objects providing manure to this allocation object | integer | n/a | — | — |
| [trn_obs](trn_obs.md) | Number of demand objects receiving manure from this allocation object | integer | n/a | — | — |

## Manure sources

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Source or receiving-object record number | integer | n/a | — | — |
| [mois_typ](mois_typ.md) | Manure moisture-type selector | string | n/a | — | — |
| [manure_typ](manure_typ.md) | Manure type name referencing an entry in fertilizer.frt | string | n/a | — | — |
| [lat](lat.md) | Latitude of the source object | real | — | — | — |
| [long](long.md) | Longitude of the source object | real | — | — | — |
| [stor_init](stor_init.md) | Initial manure storage at the source object | real | — | — | — |
| [stor_max](stor_max.md) | Maximum manure storage capacity at the source object | real | — | — | — |
| [prod_mon](prod_mon.md) | Average monthly manure production at the source object | real | — | — | — |

## Receiving objects

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Source or receiving-object record number | integer | n/a | — | — |
| [ob_typ](ob_typ.md) | Type of demand object receiving manure: hru for application | string | n/a | — | — |
| [ob_num](ob_num.md) | Number identifying the demand object of the specified type | integer | n/a | — | — |
| [dtbl](dtbl.md) | Name of the decision table governing manure or fertilizer application | string | n/a | — | — |
| [right](right.md) | Manure right designation, either sr for senior or jr for junior right | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
