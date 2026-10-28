---
description: "This file specifies which channel sediment parameters can change during soft calibration and the limits on those changes."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file specifies which channel sediment parameters can change during soft calibration and the limits on those changes.

# ch_sed_parms.sft

The file contains a title, the entry count, column headings, and the corresponding data rows shown below.

## Number of parameters

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mchp](mchp.md) | Number of calibration parameters | integer | n/a | — | — |

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [chg_typ](chg_typ.md) | Type of change to apply, one of absval, abschg, or pctchg | string | n/a | — | — |
| [neg](neg.md) | Negative limit constraining the magnitude of a downward parameter change | real | — | — | — |
| [pos](pos.md) | Positive limit constraining the magnitude of an upward parameter change | real | — | — | — |
| [lo](lo.md) | Lower bound enforced on the parameter value during calibration | real | — | — | — |
| [up](up.md) | Upper bound enforced on the parameter value during calibration | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
