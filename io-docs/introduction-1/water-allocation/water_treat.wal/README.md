---
description: "This file defines water treatment plants and their treatment levels."
---

{% hint style="info" %}
An Editor export of this format has not been verified. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file defines water treatment plants and their treatment levels.

SWAT+ looks for `water_treat.wal` in the simulation working directory; it is not selected through `file.cio`. See the [water_treatment_read.f90](https://github.com/swat-model/swatplus/blob/6f515368525e7d84089ae0f9d33f4c9115de5679/src/water_treatment_read.f90#L34) reader.

# water_treat.wal

After the title, plant count, and headings, enter each plant definition followed by its treatment-level constituent settings. Include additional pesticide or pathogen values when those constituents are configured.

## Plant count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [imax](imax.md) | Number of records | integer | n/a | — | — |

## Treatment plants

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [stor_mx](stor_mx.md) | Maximum storage capacity of the treatment plant | real | — | — | — |
| [lag_days](lag_days.md) | Lag time applied to treated outflow from the plant | real | — | — | — |
| [loss_fr](loss_fr.md) | Fraction of water lost during treatment | real | — | — | — |
| [num_treats](num_treats.md) | Number of treatment levels defined for this plant | integer | n/a | — | — |

## Treatment levels

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [org_min_typ](org_min_typ.md) | Source type for organic/mineral removal, one of const, dtbl, or recall | string | n/a | — | — |
| [org_min_name](org_min_name.md) | Name of the organic/mineral source record selected by the corresponding source-type field | string | n/a | — | — |
| [pests_typ](pests_typ.md) | Source type for pesticide removal, one of const, dtbl, or recall | string | n/a | — | — |
| [pests_name](pests_name.md) | Name of the pesticide source record selected by the corresponding source-type field | string | n/a | — | — |
| [paths_typ](paths_typ.md) | Source type for pathogen removal, one of const, dtbl, or recall | string | n/a | — | — |
| [paths_name](paths_name.md) | Name of the pathogen source record selected by the corresponding source-type field | string | n/a | — | — |
| [salts_typ](salts_typ.md) | Source type for salt ion removal, one of const, dtbl, or recall | string | n/a | — | — |
| [salts_name](salts_name.md) | Name of the salt source record selected by the corresponding source-type field | string | n/a | — | — |
| [constit_typ](constit_typ.md) | Source type for other constituent removal, one of const, dtbl, or recall | string | n/a | — | — |
| [constit_name](constit_name.md) | Name of the general-constituent source record selected by the corresponding source-type field | string | n/a | — | — |
| [descrip](descrip.md) | Descriptive text for the treatment plant | string | n/a | — | — |

## Pesticide values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [pest](pest.md) | Pesticide removal amount applied per pesticide | real | — | — | — |

## Pathogen values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [path](path.md) | Pathogen removal amount applied per pathogen | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
