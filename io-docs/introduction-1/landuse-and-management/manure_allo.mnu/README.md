---
description: "This file defines manure sources, receiving objects, and the rules used to allocate manure between them."
---

# manure\_allo.mnu

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines manure sources, receiving objects, and decision-table rules used to allocate manure in [`mallo_control.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/mallo_control.f90#L32-L77). SWAT+ looks for `manure_allo.mnu` in the simulation working directory (loaded in [`main.f90.in`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/main.f90.in#L89) via [`manure_allocation_read.f90`](https://github.com/swat-model/swatplus/blob/aa4179fea9c9fbb9b00efc38e3d4def3b6a3f715/src/manure_allocation_read.f90#L39-L117)); it is not selected through `file.cio`.

After the title and allocation count, enter each allocation-object block: object headings and definition row, source headings and `src_obs` source rows, then receiving-object headings and `trn_obs` receiver rows. Each source row ends with 12 monthly production values (`prod_mon`).

## Allocation count

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [imax](imax.md) | Number of allocation records | integer | n/a | — | — |

## Allocation objects

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [name](name.md) | Record name (read but not used in main 6f515368) | string | n/a | — | — |
| [rule\_typ](rule_typ.md) | Allocation rule type (read but not used in main 6f515368) | string | n/a | — | — |
| [src\_obs](src_obs.md) | Number of source objects providing manure to this allocation object | integer | n/a | — | — |
| [trn\_obs](trn_obs.md) | Number of demand objects receiving manure from this allocation object | integer | n/a | — | — |

## Manure sources

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [k](k.md) | Source or receiving-object record number | integer | n/a | — | — |
| [mois\_typ](mois_typ.md) | Manure moisture-type selector (`wet` or `dry`; output label only) | string | n/a | — | — |
| [manure\_typ](manure_typ.md) | Manure type name referencing an entry in `fertilizer.frt` | string | n/a | — | — |
| [lat](lat.md) | Latitude of the source object (read but not used in main 6f515368) | real | — | — | — |
| [long](long.md) | Longitude of the source object (read but not used in main 6f515368) | real | — | — | — |
| [stor\_init](stor_init.md) | Initial manure storage at the source object (read but not used in main 6f515368) | real | tons | — | — |
| [stor\_max](stor_max.md) | Maximum manure storage capacity at the source object (read but not used in main 6f515368) | real | tons | — | — |
| [prod\_mon](prod_mon.md) | Average monthly manure production (12 monthly values per row) | real | tons/month | — | — |

## Receiving objects

| **Field** | **Description** | **Type** | **Unit** | **Default** | **Range** |
| --------- | --------------- | -------- | -------- | ----------- | --------- |
| [k](k.md) | Source or receiving-object record number | integer | n/a | — | — |
| [ob\_typ](ob_typ.md) | Type of demand object receiving manure (`hru` for application) | string | n/a | — | — |
| [ob\_num](ob_num.md) | Number identifying the demand object of the specified type | integer | n/a | — | — |
| [dtbl](dtbl.md) | Name of the decision table governing manure or fertilizer application | string | n/a | — | — |
| [right](right.md) | Manure right designation (`sr` or `jr`) (read but not used in main 6f515368) | string | n/a | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
