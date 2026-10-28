---
description: "This file defines water-use objects and their storage, water-loss, and constituent settings."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines water-use objects and their storage, water-loss, and constituent settings.

SWAT+ looks for `water_use.wal` in the simulation working directory; it is not selected through `file.cio`. See the [water_use_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_use_read.f90#L35) reader.

# water_use.wal

After the title, object count, and headings, enter one object definition per row. Include the additional pesticide and pathogen rows when those constituents are configured.

## Object count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Water-use objects

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [stor_mx](stor_mx.md) | The maximum storage capacity of the object | real | — | — | — |
| [lag_days](lag_days.md) | The treatment lag time in days before outflow occurs | real | — | — | — |
| [loss_fr](loss_fr.md) | The fraction of water lost during treatment | real | — | — | — |
| [org_min_typ](org_min_typ.md) | The source type for organic/mineral constituent concentrations, one of const, dtbl, or recall | string | n/a | — | — |
| [org_min_name](org_min_name.md) | Name of the organic/mineral source record selected by the corresponding source-type field | string | n/a | — | — |
| [pests_typ](pests_typ.md) | The source type for pesticide concentrations, one of const, dtbl, or recall | string | n/a | — | — |
| [pests_name](pests_name.md) | Name of the pesticide source record selected by the corresponding source-type field | string | n/a | — | — |
| [paths_typ](paths_typ.md) | The source type for pathogen concentrations, one of const, dtbl, or recall | string | n/a | — | — |
| [paths_name](paths_name.md) | Name of the pathogen source record selected by the corresponding source-type field | string | n/a | — | — |
| [salts_typ](salts_typ.md) | The source type for salt ion concentrations, one of const, dtbl, or recall | string | n/a | — | — |
| [salts_name](salts_name.md) | Name of the salt source record selected by the corresponding source-type field | string | n/a | — | — |
| [constit_typ](constit_typ.md) | The source type for other constituent concentrations, one of const, dtbl, or recall | string | n/a | — | — |
| [constit_name](constit_name.md) | Name of the general-constituent source record selected by the corresponding source-type field | string | n/a | — | — |
| [descrip](descrip.md) | A description of the treatment object | string | n/a | — | — |

## Pesticide values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [pest](pest.md) | The pesticide loading value associated with this object | real | — | — | — |

## Pathogen values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [path](path.md) | The pathogen loading value associated with this object | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
