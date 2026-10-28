---
description: "Defines channel sediment budget calibration parameters for stream-reach regions, organizing channel widening, downcutting, headcut advance, and flood-plain accretion values by region and stream order for landscape-scale sediment transport calibration."
---

# ch_sed_budget.sft

{% hint style="info" %}
The inspected Editor has a dispatched exporter for this input format; generation depends on project settings. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines channel sediment budget calibration parameters for stream-reach regions, organizing channel widening, downcutting, headcut advance, and flood-plain accretion values by region and stream order for landscape-scale sediment transport calibration.

The reader obtains the filename through `in_chg%ch_sed_budget_sft`.

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

### Additional read at line 43

Source condition/loop: `if (.not. i_exist .or. in_chg%ch_sed_budget_sft == "null") then / else > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mreg](mreg.md) | Number of channel calibration regions to read | integer | n/a | — | — |

### Record at line 56

The repeated values follow count expression `nspu`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name.md) | Name identifying this group, region, or parameter set | string | n/a | — | — |
| [ord_num](ord_num.md) | Count of stream orders defined for this region | integer | n/a | — | — |
| [nspu](nspu.md) | Number of spatial units (reaches) described for the region | integer | n/a | — | — |
| [elem_cnt](elem_cnt.md) | Encoded element-list entry passed to define_unit_elements | integer | n/a | — | — |

### Record at line 122

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [name](name_2.md) | Name identifying this group, region, or parameter set | string | n/a | — | — |
| [chw](chw.md) | Channel widening rate used for calibration | real | — | — | — |
| [chd](chd.md) | Channel downcutting or accretion rate used for calibration | real | — | — | — |
| [hc](hc.md) | Headcut advance rate used for calibration | real | — | — | — |
| [fpd](fpd.md) | Flood-plain accretion rate used for calibration | real | — | — | — |
