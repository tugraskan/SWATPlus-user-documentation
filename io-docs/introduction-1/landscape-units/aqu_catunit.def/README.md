---
description: "Defines aquifer cataloging-unit groups and their element lists. The inspected reader also has a regional pass that reopens this same configured filename; see the source limitation below."
---

# aqu_catunit.def

{% hint style="info" %}
Editor generation of this exact format has not been verified in the inspected checkout. The table below describes the Fortran source, not an Editor export contract. Editor checkout inspected: `1efec55`.

The table values below are based on the SWAT+ Fortran source code, not an assumed SWAT+ Editor export. Field names and types may differ from Editor labels. A dash means that a unit, recommended default, or range has not been established here; it is not a Fortran initialization value.
{% endhint %}

Defines aquifer cataloging-unit groups and their element lists. The inspected reader also has a regional pass that reopens this same configured filename; see the source limitation below.

The reader obtains the filename through `in_regs%def_aqu`.

{% hint style="warning" %}
The regional pass checks `in_regs%def_aqu_reg` but opens `in_regs%def_aqu` again (aqu_read_elements.f90:86–89). Its groups below describe that second pass over the same configured file, not extra sections to append to the file. This source inconsistency has not been corrected or tested here.
{% endhint %}

## Source read groups

The tables follow distinct data-read groups in the source. Counts, conditional variants, and repeated values are shown separately. A backspace or reopening may read the same input record again, so these groups must not be treated as an unconditional sequence of extra file lines.

Before the data groups, the loading pass consumes a title record.

Before the data groups, the loading pass consumes a title record.

### Additional read at line 39

Source condition/loop: `if (i_exist .or. in_regs%def_aqu /= "null") then > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mreg](mreg.md) | Number of group or region records to read | integer | n/a | — | — |

### Data record

The repeated values follow count expression `nspu`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading record identifier read before the group or region fields | integer | n/a | — | — |
| [name](name.md) | Name of the cataloging-unit region | string | n/a | — | — |
| [area_ha](area_ha.md) | Area of the landscape cataloging unit in hectares | real | — | — | — |
| [nspu](nspu.md) | Number of encoded element-list entries for this group or region | integer | n/a | — | — |
| [elem_cnt](elem_cnt.md) | Encoded element-list entry passed to define_unit_elements | integer | n/a | — | — |

### Additional read at line 92

Source condition/loop: `if (i_exist .or. in_regs%def_aqu_reg /= "null") then > do`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [mreg](mreg.md) | Number of group or region records to read | integer | n/a | — | — |

### Additional read at line 98

Source condition/loop: `if (i_exist .or. in_regs%def_aqu_reg /= "null") then > do > do i = 1, mreg`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading record identifier read before the group or region fields | integer | n/a | — | — |
| [name](name_2.md) | Name of the regional cataloging-unit region | string | n/a | — | — |
| [area_ha](area_ha_2.md) | Area of the regional landscape cataloging unit in hectares | real | — | — | — |
| [nspu](nspu.md) | Number of encoded element-list entries for this group or region | integer | n/a | — | — |

### Additional read at line 103

Source condition/loop: `if (i_exist .or. in_regs%def_aqu_reg /= "null") then > do > do i = 1, mreg > if (nspu > 0) then`.

| Field | Description | Type | Unit | Default | Range |
| --- | --- | --- | --- | --- | --- |
| [k](k.md) | Leading record identifier read before the group or region fields | integer | n/a | — | — |
| [name](name_2.md) | Name of the regional cataloging-unit region when element counts are read | string | n/a | — | — |
| [area_ha](area_ha_2.md) | Area of the regional landscape cataloging unit in hectares when element counts are read | real | — | — | — |
| [nspu](nspu.md) | Number of encoded element-list entries for this group or region | integer | n/a | — | — |
| [elem_cnt(isp)](elem_cnt_isp.md) | Encoded element-list entry at position isp, passed to define_unit_elements | integer | n/a | — | — |
