---
description: "This file specifies plant parameters and their permitted changes during soft calibration."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file specifies plant parameters and their permitted changes during soft calibration.

# plant_parms.sft

After the title, region count, and headings, enter the region and element information, followed by the plant-parameter entries for its land uses. See the format limitation below before preparing this file.

{% hint style="warning" %}
The current model interprets the parameter-count and element-count positions inconsistently when loading the region row. Treat this layout as provisional until that discrepancy is resolved.
{% endhint %}

## Region count

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mreg](mreg.md) | Number of regions | integer | n/a | — | — |

## Regions and elements

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [lum_num](lum_num.md) | Number of land uses defined within the region | integer | n/a | — | — |
| [parms](parms.md) | Number of plant parameters used in calibration for the region | integer | n/a | — | — |
| [nspu](nspu.md) | Number of element-list entries | integer | n/a | — | — |
| [elem_cnt](elem_cnt.md) | Element-list entry | integer | n/a | — | — |

## Plant parameters

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [var](var.md) | Variable name identifying which plant parameter is being calibrated | string | n/a | — | — |
| [name](name_2.md) | Record name | string | n/a | — | — |
| [init_val](init_val.md) | Initial calibration value for the named plant parameter | real | — | — | — |
| [chg_typ](chg_typ.md) | Type of change applied to the parameter during calibration (absval, abschg, or pctchg) | string | n/a | — | — |
| [neg](neg.md) | Negative limit applied to the parameter per calibration iteration | real | — | — | — |
| [pos](pos.md) | Positive limit applied to the parameter per calibration iteration | real | — | — | — |
| [lo](lo.md) | Ultimate lower limit of the parameter, enforced via a Max operation | real | — | — | — |
| [up](up.md) | Ultimate upper limit of the parameter, enforced via an amin1 operation | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
