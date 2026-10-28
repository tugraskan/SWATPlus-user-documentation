---
description: "This file supplies regional channel sediment targets for soft calibration."
---

{% hint style="info" %}
The inspected SWAT+ Editor has an exporter for this format. Field names and values in the table are based on the SWAT+ Fortran source. A dash means that a unit, recommended default, or range has not been established.
{% endhint %}

This file supplies regional channel sediment targets for soft calibration.

# ch_sed_budget.sft

The file contains a title, the entry count, column headings, and the corresponding data rows shown below.

## Number of regions

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mreg](mreg.md) | Number of regions | integer | n/a | — | — |

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Record name | string | n/a | — | — |
| [ord_num](ord_num.md) | Count of stream orders defined for this region | integer | n/a | — | — |
| [nspu](nspu.md) | Number of element-list entries | integer | n/a | — | — |
| [elem_cnt](elem_cnt.md) | Element-list entry | integer | n/a | — | — |

## Input values

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name_2.md) | Record name | string | n/a | — | — |
| [chw](chw.md) | Channel widening rate used for calibration | real | — | — | — |
| [chd](chd.md) | Channel downcutting or accretion rate used for calibration | real | — | — | — |
| [hc](hc.md) | Headcut advance rate used for calibration | real | — | — | — |
| [fpd](fpd.md) | Flood-plain accretion rate used for calibration | real | — | — | — |

**Type note:** `string` means Fortran `character`; `integer` and `real` use the same names in Fortran.
